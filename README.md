# An overview of HTTP Verbs on REST API services 

## Using HTTP Methods for RESTful Services

- The primary or most-commonly-used HTTP verbs or methods are POST, GET, PUT, and DELETE

##

| HTTP verbs | Operations |
---------------------------
| POST | Create |
| GET | Read |
| PUT | Update |
| DELETE | Delete |


- GET
  *The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.

- POST
  *The POST method is used to submit an entity to the specified resource, often causing a change in state or side effects on the server

- PUT
  *The PUT method replaces all current representations of the target resource with the request payload.

- DELETE
  *The DELETE method deletes the specified resource.






## Long Request URLs

- URL has a practical length limitation, typically between 2k to 8k. It's enforced by some browsers and proxies. If your API uses GET requests with URLs that exceed the length limitation, such requests may be rejected by browsers. To bypass the limitation, the client code should use a POST request with Content-Type of application/x-www-form-urlencoded along with HTTP header X-HTTP-Method-Override: GET. This approach also works for DELETE requests.

## HTTP Methods (Verbs)

- If the request URLs follow the REST model, their HTTP methods are specified as part of the API specification. In particular, every API method must comply with the requirements of HTTP protocol based on the specific HTTP Verb to which the API method maps. For details, please refer to the Hypertext Transfer Protocol specification and the PATCH Method RFC.

- Safe Methods, such as HTTP GET and HEAD should not represent an action other than retrieval. Specifically, HTTP GET ought to be considered safe and should not have any client-visible side-effects.

- Idempotence in HTTP means that the side-effects of multiple identical requests are the same as for a single request. GET, PUT, and DELETE are the idempotent HTTP methods relevant to the style guide. Note that idempotence is only expressed in terms of server side-effects and does not specify anything about the response. In particular DELETE for non-existing resources should return 404 (Not Found).

##

| HTTP Verb	| Safe | Idempotent |	
---------------------------------
| GET | Yes | Yes |
| PUT | | Yes |
| DELETE | |	Yes |
| POST | | |
| PATCH	| | |
---------------------------------

