# HotelReservation microservices and distributed cloud Blueprint
There are a plenty of examples of different of microservices that utilize .Net Core as platform as domain designs. The one comes to mind is documented quite well by Microsoft EShopContainers Microfrontend blueprints.
For Python, there a quite few Git examples utilizing Fast API as a library but a scarcity of a business domain examples.  The one notable exception, is a book by Harry Percival and Bob Gregoory  -  Architecture Patterns with Python that covers pretty well an example of microfrontends and microservices utilizing Flask API.  These examples have provided an inspiration for creation of a fictional Hotel Reservation microservices application that utilizes FastApi in the Azure's Kubernettes Service (AKS) and Amazon Elastic Kubernetes Service (EKS).  The services use CQRS pattern as well.   The one wrinkle that hasn't been explored before in Python implementations is a concept of tying  together a Middleware Pattern, Event Sourcing and a Circuit Breaker as retry mechanism for peer-to-peer distributed communication. The usual and a customary approach is to utilize either Kafka or Red Pandas for publisher-subscriber message queues.   But the message queue itself becomes a single point of failure.  The cloud standards groups this author was part of eschewed Kafka and relied on Event Bus or Event Hub in Azure instead due to Kafka's complexity of having to maintain ZooKeeper.  This repo will explore ideas base on Saga choreoagraphy pattern and peer-to-peer microservices design along with archival of event stores in any cloud based blob storage or structured database like PostgreSQL.  Some of these ideas are based on BFF pattern that is often utilized as gateway to UI applications.

This pattern provides a modern pipeline approach for execution of different type of http commands/querries and is used to provide added scalability when the applicaiton is deployed to Azure AKS or any other containerized eco-systems.

Reference: https://microservices.io/patterns/data/saga.html




