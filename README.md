# Airbnb Clone Project
## Project Overview
This Airbnb clone project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It will provide a robust and scalable foundation for managing user interactions, property listings, bookings, and payments.

**🚀Goals**
1. User Management: Implement a secure user registration, authentication, and profile management system.
2. Property Management: Develop property listing creation, updates, and retrieval features.
3. Booking System: Create a booking mechanism for users to reserve properties and manage booking details.
4. Payment Processing: Integrate a payment system to handle transactions and record payment details.
5. Review system: Allow users to leave reviews and ratings for properties.
6. Data Optimization: Ensure efficient data retrieval and storage through database optimizations.

**🛠️Technology Stack**
- Django REST Framework
- PostgreSQL
- GraphQL
- Celery
- Redis
- Docker
- CI/CD Pipelines

## Team Roles
- Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
- Database Administrator: Manages database design, indexing, and optimizations.
- DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
- QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.

## Technology Stack Overview
- Django REST Framework: A web framework for building RESTful APIs.
- PostgreSQL: A powerful, open-source relational database management system.
- GraphQL: A query language for APIs and a runtime for fulfilling those queries with your data.
- Celery: An open-source Python library used to run tasks asynchronously in the background.
- Redis: An open-source, in-memory data structure used as a database, cache, and message broker.
- Docker: A software platform that automates the deployment of applications within containers, offering a standardized and portable way to package and run applications in various environments.
- CI/CD Pipelines: Automated series of steps that streamline the software development lifecycle from code creation to deployment.

## Database Design Overview
**Entities:**
1. Users: Represent guests and hosts. A host can own many properties. A host has only one profile but can also have a user profile. A guest can make many bookings.
   - id(Unique Identifier)
   - name
   - email
   - password_hash
   - user_type e.g. "host", "guest"
2. Properties: A property can only belong to one host. A property can have many scheduled bookings. It can also have many reviews and many amenities.
   - Property_id
   - image
   - amenities
   - description
   - price(included_in_price)
   - extra_cost
   - is_available
3. Booking: A reservation made by a guest. Each booking is made by one guest. A booking can have one complete payment or more(if paying in parts). 
   - booking_id
   - user_id(Foreign Key to user)
   - property_id(Foreign Key to property)
   - check_in_date
   - check_out_date
4. Payment: Tracks payments for bookings. Each payment belongs to a single property.
   - payment_id
   - booking_id(Foreign Key to booking)
   - amount
   - payment_method(e.g. paypal)
   - payment_status(e.g. pending, completed)
5. Review: Feedback from a guest after the stay. Each review is for one property, and it is written by one user.
   - review_id
   - user_id (Foreign Key to user)
   - property_id (Foreign Key to property)
   - rating (1-5)
   - comment
6. Amenity: Features of a property.
   - amenity_id
   - amenity_name
   - description

## Feature Breakdown
1. User Management: Register new users, log in, authenticate, and manage user profiles.
Users can sign up as guests  or hosts, manage their personal information, and access role-specific functionalities.
3. Property Management: Hosts can create, update, retrieve, and delete property listings. Each listing includes details such as title, description, and amenities, allowing hosts to showcase their properties effectively.
4. Booking system: Guests can make, update, and manage bookings, including check-in and check-out. The system prevents double bookings, tracks reservation status, and calculates total cost based on stay duration and pricing.
6. Review system: Allows guests to post and manage reviews for properties. This builds trust in the platform, provides valuable feedback to hosts, and helps future guests make informed decisions.
7. Payment processing: Handle payment transactions related to bookings. Users can pay for bookings online at their convenience while hosts receive payouts for confirmed stays, ensuring a smooth financial workflow.
8. Database optimizations:
Indexing: Implement indexes for fast retrieval of frequently accessed data.
Caching: Use caching strategies to reduce database load and improve performance.
