## What does REST stand for?

Representational State Transfer

## REST APIs are designed around a resources.

## What is an identifer of a resource? Give an example.

URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:


## What are the most common HTTP verbs?

 GET, POST, PUT, PATCH, and DELETE.

## What should the URIs be based on?

hypermedia links 

## Give an example of a good URI.

Stability over time
Short
Give the user an idea what is linked
Easy to type
Easy to guess (relevant only for a few links like "/jobs")
Search engine friendly
URI schema should be consistent over the whole site
URI schema should allow future extensions

## What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

Chatty services tend to be ones that return simplified information and use more fine-grained operations. Chunky services tend to return complex hierarchies of information and use coarse operations. In other words, the difference is that chatty services require more calls than chunky services to return the same information but allow more flexibility to return only the information that is actually required.

## What status code does a successful GET request return?

200 - the server successfully returned the page

## What status code does an unsuccessful GET request return?

If not valid, 400 Bad Request is returned

## What status code does a successful POST request return?

 201 status code 

## What status code does a successful DELETE request return?

404 
