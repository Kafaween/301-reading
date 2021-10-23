# Real time messaging with websockets

## What is WebSocket?
The web has traveled a long way to support full-duplex (or two-way) communication between a client and server. This is the prime intention of the WebSocket protocol: to provide persistent real-time communication between the client and the server over a single TCP socket connection.

The WebSocket protocol has only two agendas : 1.) to open up a handshake, and 2.) to help the data transfer. Once the server and client both have their handshakes in, they can send data to each other with less overhead at will.

WebSocket communication takes place over a single TCP socket using either WS (port 80) or WSS (port 443) protocol. Almost every browser except Opera Mini provides admirable support for WebSockets at the time of writing, as per Can I Use.



Avanthika Meenakshi 
First, solve the problem. Then, write the code.
WebSockets tutorial: How to go real-time with Node and React
January 8, 2021  6 min read 

WebSockets Tutorial With Node And React
Are you wondering why we publish all this free content that you always seem to stumble on when Googling stuff? Simple: trials!
If you’re enjoying LogRocket’s blog, we bet you’ll love our product. LogRocket helps you reproduce bugs more quickly, understand frontend performance issues, and see exactly how users interact with your React apps. Try LogRocket Pro for free for 14 days.
Editor’s note: This WebSockets tutorial was updated on 1/19/2021.

What is WebSocket?
The web has traveled a long way to support full-duplex (or two-way) communication between a client and server. This is the prime intention of the WebSocket protocol: to provide persistent real-time communication between the client and the server over a single TCP socket connection.

The WebSocket protocol has only two agendas : 1.) to open up a handshake, and 2.) to help the data transfer. Once the server and client both have their handshakes in, they can send data to each other with less overhead at will.

WebSocket communication takes place over a single TCP socket using either WS (port 80) or WSS (port 443) protocol. Almost every browser except Opera Mini provides admirable support for WebSockets at the time of writing, as per Can I Use.



## How is WebSocket different than HTTP polling, HTTP streaming, and server-sent events?
Historically, creating web apps that needed real-time data (like gaming or chat apps) required an abuse of HTTP protocol to establish bidirectional data transfer. There were multiple methods used to achieve real-time capabilities, but none of them were as efficient as WebSockets. HTTP polling, HTTP streaming, Comet, SSE — they all had their own drawbacks.

## HTTP polling
The very first attempt to solve the problem was by polling the server at regular intervals. The HTTP long polling lifecycle is as follows:

The client sends out a request and keeps waiting for a response.
The server defers its response until there’s a change, update, or timeout. The request stayed “hanging” until the server had something to return to the client.
When there’s some change or update on the server end, it sends a response back to the client.
The client sends a new long poll request to listen to the next set of changes.
There were a lot of loopholes in long polling — header overhead, latency, timeouts, caching, and so on.

## HTTP streaming
This mechanism saved the pain of network latency because the initial request is kept open indefinitely. The request is never terminated, even after the server pushes the data. The first three lifecycle methods of HTTP streaming are the same in HTTP polling.

When the response is sent back to the client, however, the request is never terminated; the server keeps the connection open and sends new updates whenever there’s a change.

## Server-sent events (SSE)
With SSE, the server pushes data to the client. A chat or gaming application cannot completely rely on SSE. The perfect use case for SSE would be, e.g., the Facebook News Feed: whenever new posts comes in, the server pushes them to the timeline. SSE is sent over traditional HTTP and has restrictions on the number of open connections.

These methods were not just inefficient, the code that went into them also made developers tired.

## Why you should use WebSockets
WebSockets are designed to supersede the existing bidirectional communication technologies. The existing methods described above are neither reliable nor efficient when it comes to full-duplex real-time communications.

WebSockets are similar to SSE but also triumph in taking messages back from the client to the server. Connection restrictions are no longer an issue since data is served over a single TCP socket connection.

How to use WebSockets
As mentioned in the introduction, the WebSocket protocol has only two agendas. Let’s see how WebSockets fulfills those agendas. To do that, I’m going to spin off a Node.js server and connect it to a client built with React.js.

