# API Design Best Practices

## What does REST stand for?
REST stands for Representational State Transfer.

## REST APIs are designed around a ____.
REST APIs are designed around resources. the resources are the data the client can access it. each resource has a unique identifier.

## What is an identifer of a resource? Give an example.
The identifier of a resource  is a unique identifier to distinguish it from other resources.for example the `URI` can identifies order for a specific user.

`https://adventure-works.com/orders/1`

## What are the most common HTTP verbs?
The most common HTTP verbs are `GET, POST, PUT, PATCH, and DELETE`.
## What should the URIs be based on?
The URIs should be based on nouns of resources and not the verbs (The actions we apply on these resources)
`https://adventure-works.com/orders // Good`
`https://adventure-works.com/create-order // Bad`

# Give an example of a good URI.
`https://adventure-works.com/orders`

## What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
Chatty web API is a bad thing. It occures when the customer do a large number of requests to get data. It consumes the server and makes overload on it.

## What status code does a successful GET request return?
The succesful GET request returns HTTP status code 200 (OK).
## What status code does an unsuccessful GET request return?
The unsuccesful GET request returns returns HTTP status code 404. It means the resource is `not found`
## What status code does a successful POST request return?

* a successful POST request should return HTTP status code 201. It means the new resources was created.
* in some cases POST request return HTTP status code 200. It dose not mean that it is successfull.

## What status code does a successful DELETE request return?

DELETE request returns HTTP status code 204. It indicates that the resources has been deleted.If the resource is not existed it will return 404 (not found).


## Things I want to know more about.


I want to know more about the HTTP protocol and about REST designe.


[RESTful web API design](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)