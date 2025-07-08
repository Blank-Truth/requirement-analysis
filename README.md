Requirement Analysis in Software Development.

This repository is meant to highlight the necessary features and requirements for any Software Development project.

What is Requirement Analysis?

Requirement analysis is the process of determining the needs and expectations of a a new or modified product or system. 
It involves gathering, analyzing, and documenting these needs to ensure that the final product meets user expectations and business goals. 
This crucial phase helps to avoid costly mistakes and delays by ensuring everyone has a clear understanding of what the product should do. 

Why is Requirement Analysis Important ?

1. Avoids Costly Mistakes

Fixing errors early is cheaper than during development or after release.

2. Aligns Stakeholders

Ensures everyone (clients, developers, testers) shares the same goals and expectations.

3. Guides Development and Testing

Provides a clear blueprint for building and verifying the software.


Key Activities in Requirement Analysis.

1. Requirement Gathering
Collect raw information about the desired system from stakeholders.

Sources include clients, users, market analysis, and existing systems.

Focuses on identifying what the users need without yet analyzing or refining it.

Techniques: stakeholder interviews, observations, document reviews.

2. Requirement Elicitation
Actively draw out requirements through direct interaction with stakeholders.

Aims to clarify, uncover hidden needs, and resolve conflicting expectations.

Techniques: interviews, questionnaires, workshops, brainstorming, use cases, prototyping.

3. Requirement Documentation
Formally record the gathered and elicited requirements in a structured format.

Produces the Software Requirements Specification (SRS) or Product Requirements Document (PRD).

Ensures all requirements are clear, complete, and traceable.

Should include functional, non-functional, business, and user requirements.

4. Requirement Analysis and Modeling
Analyze the requirements for clarity, consistency, feasibility, and completeness.

Identify dependencies, priorities, and possible conflicts.

Create models to visualize the system: use case diagrams, data flow diagrams (DFD), ER diagrams, etc.

Helps in understanding the scope and complexity of the system.

5. Requirement Validation
Ensure the documented requirements truly reflect the stakeholders' needs.

Confirm requirements are accurate, complete, testable, and achievable.

Techniques: reviews, walkthroughs, inspections, and early prototyping.

Prevents building the wrong system or missing key features.


Types of Requirements.

✅ Functional Requirements
(These define what the system must do)

. Hotel Listing Management

Enable hotel owners/managers to add, update, or delete hotel information via a separate portal interface.

. Search Interface for Users

Allow customers to search hotels from the CDN-backed portal, showing recommendations, nearby options, and offers retrieved via ElasticSearch.

. Booking Process

Facilitate room booking through a booking service that interacts with payment services and persists reservations in the booking database.

. Booking History Viewing

Provide a “View Booking” service for users and managers to retrieve both current and past bookings using Redis cache and Cassandra for storage.

. Notifications

Send notifications (booking confirmations, status updates, offers) via Kafka-triggered consumers for managers and customers.


⚙️ Non-functional Requirements
(These define how well the system performs)

. High Throughput & Scalability

Use microservices and partitioned clusters (e.g., Hotel DB master-slave, separate customer/search/booking clusters) to handle large volumes of traffic 

. Low Latency Search & Booking

Display hotel listings quickly via ElasticSearch and cache recent booking data using Redis to minimize response time.

. Data Consistency and Integrity

Ensure booking accuracy by coordinating data updates across multiple stores (Redis, booking DB, Cassandra, Kafka queue).

. Reliability and Fault Tolerance

Distribute services across clusters, use messaging queues, and replicate data (master-slave DB, backup in Cassandra) to prevent single points of failure.

. Real-time Notifications & Analytics

Process event streams via streaming services like Kafka and Hadoop to support timely notifications and analytical insights.


Use Case Diagrams.

A Use Case Diagram is a visual representation of the interactions between users (actors) and a system, showing the different ways (use cases) the system is used to achieve specific goals. It is part of UML (Unified Modeling Language) and helps capture functional requirements in a simple, intuitive format.

![alx-booking-uc](https://github.com/user-attachments/assets/ba470027-d339-43d4-82de-54b4a0ad7d90)


Acceptance Criteria.

Acceptance Criteria are the specific, measurable conditions that a software product or feature must meet to be accepted by stakeholders (typically the client or product owner). They are written during requirement analysis to define “done” for each feature.

🛒 Example: Acceptance Criteria for the Checkout Feature
(Booking Management System)

💡 User Story:
As a customer, I want to check out securely so that I can confirm my hotel booking and receive a receipt.

✅ Acceptance Criteria:
✅ The system must display a summary of the booking (hotel, room, dates, price).

✅ The user must be able to enter or select a saved payment method.

✅ Payment must be processed through a secure payment gateway.

✅ The system must show a success message after successful payment.

✅ The booking must be stored in the booking database.

✅ The customer must receive a confirmation email and SMS with the booking ID.

✅ If payment fails, the user must be shown an error and allowed to retry.

✅ The checkout process must complete within 5 seconds under normal conditions.
