# HotelReservation microservices and distributed cloud Blueprint
There are a plenty of examples of different of microservices that utilize .Net Core as platform as domain designs. The one comes to mind is documented quite well by Microsoft EShopContainers Microfrontend blueprints.
For Python, there a quite few Git examples utilizing Fast API as a library but a scarcity of a business domain examples.  The one notable exception, is a book by Harry Percival and Bob Gregoory  -  **Architecture Patterns with Python** that covers pretty well an example of microfrontends and microservices while utilizing Flask API.  This manuscript have provided an inspiration for a creation of a fictional Hotel Reservation microservices application that utilizes Fast Api in the Azure's Kubernettes Service (AKS) and Amazon Elastic Kubernetes Service (EKS).  The services use CQRS pattern as well.   The one wrinkle that hasn't been explored before in Python implementations is a concept of tying  together a Middleware Pattern, Event Sourcing and a Circuit Breaker patten for peer-to-peer distributed communication. The usual and a customary approach is to utilize either Kafka or Red Pandas for publisher-subscriber message queues.   But the message queue itself becomes a single point of failure.  The cloud standards groups this author was part of eschewed Kafka and relied on Event Bus or Event Hub in Azure instead due to Kafka's complexity of having to maintain ZooKeeper.  This repo will explore ideas base on Saga choreoagraphy pattern and peer-to-peer microservices.  The design will utilize archival of event stores in any cloud based blob storage provider or structured database like PostgreSQL.  Some of these ideas are based on the BFF pattern previoulsy used in authors work.  The BFF API gateway pattern is used to simplify UI frontends communication to the backend APIs.

This pattern provides a modern pipeline approach for execution of different type of http commands/querries and is used to provide added scalability when the applicaiton is deployed to Azure AKS or any other containerized eco-systems.

Reference: https://microservices.io/patterns/data/saga.html and https://github.com/eventuate-tram/eventuate-tram-core


## Scope for the project
*  Develop distributed mico-services for managing hotel reservations, check-ins, upgrades and potential machine learning integration for seasonal predictions.
## The core technololgy covered by blueprint: 
* CQRS (Command Query Responsibility Segregation) for execution of HTTPs requests.
* Event Sourcing and Event Store for both event notification and event publishing.
* Middleware Pattern - for logging, authenticaion with OpenID, request throttoling.
* Circuit Breaker design - for the request retry mechanisms.  
* Saga choreagrphy methodology to enable peer-to-peer event communication between microservices.
 
Python will be primary DSL for this implementation. The FAST Api is a web framerwork for constucting application.  PostgreSQL will be used for event logging in oroder to assure durability of messages.

The services will expose HTTP endpoints to perform CRUD (Create, Read, Update, Delete) operations on hotel reservations, rooms, and customers. These service should handle various business scenarios, such as creating a new reservation, checking room availability, updating reservation details, and deleting a reservation. The service should also manage hotel room details and customer information efficiently.  The Saga 

