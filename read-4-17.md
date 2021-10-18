# Spring Boot and OAuth2

The samples are all single-page apps using Spring Boot and Spring Security on the back end. They also all use plain jQuery on the front end. But, the changes needed to convert to a different JavaScript framework or to use server-side rendering would be minimal.

1. simple: a very basic static app with just a home page and unconditional login via Spring Boot’s OAuth 2.0 configuration properties (if you visit the home page, you will be automatically redirected to GitHub).

2. click: adds an explicit link that the user has to click to login.

3. logout: adds a logout link as well for authenticated users.

4. two-providers: adds a second login provider so the user can choose on the home page which one to use.

5. custom-error: adds an error message for unauthenticated users, and a custom authentication based on GitHub’s API.

Securing the Application with GitHub and Spring Security
To make the application secure, you can simply add Spring Security as a dependency. Since you’re wanting to do a "social" login (delegate to GitHub), you should include the Spring Security OAuth 2.0 Client starter:

```
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-oauth2-client</artifactId>
</dependency>
```

**Add a New GitHub App**

To use GitHub’s OAuth 2.0 authentication system for login, you must first Add a new GitHub app.

Select "New OAuth App" and then the "Register a new OAuth application" page is presented. Enter an app name and description. Then, enter your app’s home page, which should be http://localhost:8080, in this case. Finally, indicate the Authorization callback URL as http://localhost:8080/login/oauth2/code/github and click Register Application.

The OAuth redirect URI is the path in the application that the end-user’s user-agent is redirected back to after they have authenticated with GitHub and have granted access to the application on the Authorize application page.


**Conclusion**
We have seen how to use Spring Boot and Spring Security to build apps in a number of styles with very little effort. The main theme running through all of the samples is authentication using an external OAuth 2.0 provider.

All of the sample apps can be easily extended and re-configured for more specific use cases, usually with nothing more than a configuration file change. Remember if you use versions of the samples in your own servers to register with GitHub (or similar) and get client credentials for your own host addresses. And remember not to put those credentials in source control!
