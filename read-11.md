 # What is OAuth?
OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential


# Give an example of what using OAuth would look like.
when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you.

# How does OAuth work? What are the steps that it takes to authenticate the user? (Links to an external site.)

1-The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

2+The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

3-The first site gives this token and secret to the initiating user’s client software.

4-The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site)


5-If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

6-The user approves (or their software silently approves) a particular transaction type at the first website.

7-The user is given an approved access token (notice it’s no longer a request token).

8-The user gives the approved access token to the first website.

9-The first website gives the access token to the second website as proof of authentication on behalf of the user.

10-The second website lets the first website access their site on behalf of the user.

11-The user sees a successfully completed transaction occurring.

12-OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons)


## Authorization and Authentication flows

What is the difference between authorization and authentication? Authentication is the process of verifying who a user is. Authentication is the process of verifying who a user is.

## What is Authorization Code Flow?

The authorization code grant type is used to obtain both access tokens and refresh tokens and is optimized for confidential clients.

## What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?

What is Implicit Flow with Form Post? As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets.

What is Resource Owner Password Flow? This grant type is suitable for clients capable of obtaining the resource owner’s credentials (username and password, typically using an interactive form).



## Things I want to know more about.
