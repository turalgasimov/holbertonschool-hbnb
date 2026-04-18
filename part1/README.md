🏠 HBnB Evolution – Technical Architecture Documentation
1. Introduction

The HBnB Evolution project is a simplified version of an AirBnB-like system that allows users to register, list properties, leave reviews, and manage amenities.

This technical documentation provides a detailed blueprint of the system’s architecture and serves as a reference throughout the implementation and maintenance phases. It outlines:

    The overall architecture of the application.
    The business logic layer design (core entities and relationships).
    The API interaction flows showing how each layer communicates.

The document follows UML conventions and uses Mermaid.js syntax for diagrams, enabling clear visualization and collaborative versioning.
2. High-Level Architecture

The HBnB Evolution system uses a three-layered architecture separated into:

    Presentation Layer (Services, API) – Handles user interactions and exposes endpoints.
    Business Logic Layer (Models) – Encapsulates the core domain logic and business rules.
    Persistence Layer (Repositories, Database) – Manages data storage and retrieval.

The Facade Pattern simplifies communication between layers by exposing a clean and unified interface for higher layers to use without direct coupling.
High-Level Package Diagram
Explanation

    Presentation Layer: Contains APIs and user-facing services that handle input, output, and validation.
    Business Logic Layer: Implements rules and workflows using core entities (User, Place, Review, Amenity).
    Persistence Layer: Provides database operations through repositories and ORM models.
    Facade Pattern: Reduces inter-layer complexity, allowing the Presentation Layer to communicate with the Business Logic Layer through unified service calls.

3. Business Logic Layer
Detailed Class Diagram
Explanation

    User: Represents a system user (admin or regular) who owns multiple Places and writes Reviews.
    Place: Represents a rental listing with attributes such as title, description, price, and geolocation.
    Review: Connects User and Place, containing rating and comment details.
    Amenity: Represents features like Wi-Fi or Pool and has a many-to-many relationship with Place.

All entities share:

    Unique UUID identifier.
    Created_at and updated_at timestamps for auditing.
    CRUD methods to operate through services.

4. API Interaction Flow

The sequence diagrams below show how requests flow through the Presentation, Business Logic, and Persistence Layers for key API use cases.
4.1 User Registration
4.2 Place Creation
4.3 Review Submission
4.4 Fetching a List of Places
5. Summary and Next Steps