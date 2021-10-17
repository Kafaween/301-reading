# Spring Authuntication 

## Authentication 

Application security boils down to two more or less independent problems: authentication (who are you?) and authorization (what are you allowed to do?).

**Authentication**
The main strategy interface for authentication is AuthenticationManager, which has only one method:

```
public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}
```

An AuthenticationManager can do one of 3 things in its authenticate() method:

1. Return an Authentication (normally with authenticated=true) if it can verify that the input represents a valid principal.

2. Throw an AuthenticationException if it believes that the input represents an invalid principal.

3. Return null if it cannot decide.

The most commonly used implementation of AuthenticationManager is ProviderManager, which delegates to a chain of AuthenticationProvider instances. An AuthenticationProvider is a bit like an AuthenticationManager, but it has an extra method to allow the caller to query whether it supports a given Authentication type:

```
public interface AuthenticationProvider {

	Authentication authenticate(Authentication authentication)
			throws AuthenticationException;

	boolean supports(Class<?> authentication);
}
```

## Authorization or Access Control

Once authentication is successful, we can move on to authorization, and the core strategy here is AccessDecisionManager. There are three implementations provided by the framework and all three delegate to a chain of AccessDecisionVoter instances, a bit like the ProviderManager delegates to AuthenticationProviders.

An AccessDecisionVoter considers an Authentication (representing a principal) and a secure Object, which has been decorated with ConfigAttributes:

Syntax:

```
boolean supports(ConfigAttribute attribute);

boolean supports(Class<?> clazz);

int vote(Authentication authentication, S object,
        Collection<ConfigAttribute> attributes);
```

The ConfigAttributes are also fairly generic, representing a decoration of the secure Object with some metadata that determines the level of permission required to access it. ConfigAttribute is an interface. It has only one method (which is quite generic and returns a String), so these strings encode in some way the intention of the owner of the resource, expressing rules about who is allowed to access it. A typical ConfigAttribute is the name of a user role (like ROLE_ADMIN or ROLE_AUDIT), and they often have special formats (like the ROLE_ prefix) or represent expressions that need to be evaluated.

**Web Security**

Spring Security in the web tier (for UIs and HTTP back ends) is based on Servlet Filters, so it is helpful to first look at the role of Filters generally. The following picture shows the typical layering of the handlers for a single HTTP request.

![image](https://github.com/spring-guides/top-spring-security-architecture/raw/main/images/filters.png)

**Request Matching for Dispatch and Authorization**

A security filter chain (or, equivalently, a WebSecurityConfigurerAdapter) has a request matcher that is used to decide whether to apply it to an HTTP request. Once the decision is made to apply a particular filter chain, no others are applied.

Within a filter chain, you can have more fine-grained control of authorization by setting additional matchers in the HttpSecurity configurer, as follows:

```
@Configuration
@Order(SecurityProperties.BASIC_AUTH_ORDER - 10)
public class ApplicationConfigurerAdapter extends WebSecurityConfigurerAdapter {
  @Override
  protected void configure(HttpSecurity http) throws Exception {
    http.antMatcher("/match1/**")
      .authorizeRequests()
        .antMatchers("/match1/user").hasRole("USER")
        .antMatchers("/match1/spam").hasRole("SPAM")
        .anyRequest().isAuthenticated();
  }
}
```

**Working with Threads**

The basic building block is the SecurityContext, which may contain an Authentication (and when a user is logged in it is an Authentication that is explicitly authenticated). You can always access and manipulate the SecurityContext through static convenience methods in SecurityContextHolder, which, in turn, manipulate a ThreadLocal. The following example shows such an arrangement:

```
SecurityContext context = SecurityContextHolder.getContext();
Authentication authentication = context.getAuthentication();
assert(authentication.isAuthenticated);
```

If you need access to the currently authenticated user in a web endpoint, you can use a method parameter in a @RequestMapping, as follows:

```
@RequestMapping("/foo")
public String foo(@AuthenticationPrincipal User user) {
  ... // do stuff with user
}
```

If Spring Security is in use, the Principal from the HttpServletRequest is of type Authentication, so you can also use that directly:

```
@RequestMapping("/foo")
public String foo(Principal principal) {
  Authentication authentication = (Authentication) principal;
  User = (User) authentication.getPrincipal();
  ... // do stuff with user
}
```

