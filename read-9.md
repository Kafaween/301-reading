# Review: High-level HTTP

## The HTTP Request Lifecycle

1. At first the browser need to convert the (www.example.com) to an *IP address* if it does not already know it. If it knows it, nothing happens at this point. If it does not know it, it contacts a DNS server to resolve the name.

2. Then browser will open a TCP connection to the IP address of 9www.example.com) and send a HTTP GET request over.

3. The server software will get this HTTP request. It will somehow generate a HTTP response and send that back trough the TCP connection. How the server does this is server software dependent.

4. When the browser gets the response, it typically renders it on screen. The HTTP request is now done.



# Java HTTP Request example

We can perform HTTP requests in Java by using the built-in Java class **HttpUrlConnection**. 

## Creating a Request

* We can create an HttpUrlConnection instance using the `openConnection()` method of the URL class.

* The HttpUrlConnection class is used for all types of requests by setting the requestMethod attribute (GET, POST, PUT, DELET).

## Adding Request Parameters

To add parameters to the request we have to use the `setDoOutput(true)` method. 

## Setting Request Headers

* Adding headers to a request can be achieved by using the `setRequestProperty()` method: `con.setRequestProperty("Content-Type", "application/json");`

* To read the value of a header from a connection, we can use the `getHeaderField()` method: `String contentType = con.getHeaderField("Content-Type");`

## Configuring Timeouts

We can set the connect and read timeout by using `setConnectTimeout()` and `setReadTimeout()` methods.

## Reading the Response

To execute the request, we can use the `getResponseCode()`, `connect()`, `getInputStream()` or ` getOutputStream()` methods.
