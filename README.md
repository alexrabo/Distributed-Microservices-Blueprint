# HotelReservation microservices and MiddleWare Blueprint
There plenty of examples of different of microservices that utilize .Net Core as platform. These are documented quite well by Microsoft EShopContainers Microfrontend blueprints.
For Python implementaiton there seems to be a scarcity of examples.  The one notable exception, is a book by Harry Percival and Bob Gregoory  -  Architecture Patterns with Python that covers pretty well
an example of microfrontends and microservices utilizing Flask API.  These examples have provided an inspiration for creation of a fictional Hotel Reservation microservices application that utilizes FastApi instead and provides a deployment scenario to Azure Kubrernettes.  The services use CQRS pattern as well.   The one wrinkle that hasn't been explored before in Python implementations is concept of Middleware Pattern.
This pattern provides a modern pipeline approach for execution of different type of http commands/querries and is used to provide added scalability when the applicaiton is deployed to Azure AKS or any other containerized eco-system.

Here are the highlights of this implemetation:

Middleware Pattern in FastAPI
The pattern will include custom middleware that:

•	Validates requests.
•	Handles exceptions.
•	Logs incoming requests and outgoing responses.
•	Manages cross-cutting concerns (e.g., authentication, authorization).

In addition following benefits can be derived from this approach:

•	AuthenticationMiddleware: To handle user authentication.
•	AuthorizationMiddleware: To handle role-based access control (RBAC).
•	CachingMiddleware: To cache certain responses.
•	ThrottlingMiddleware: To limit the number of requests per client.




