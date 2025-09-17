# airbnb-clone-project

## Overview
The **AirBnB Clone Project** is a simplified version of the AirBnB web application.  
The goal is to understand how full-stack applications work by building key features step by step.

## Project Goals
- Build a command-line interpreter to manage AirBnB objects.  
- Create a front-end that interacts with the back-end.  
- Develop a RESTful API to connect with the front-end.  
- Store and manage data using databases.  
- Practice collaboration and version control with GitHub.  

## Tech Stack
- **Python** (Back-end & CLI)  
- **Flask / FastAPI** (Web framework)  
- **MySQL / SQLite** (Database)  
- **HTML, CSS, JavaScript** (Front-end)  
- **Git & GitHub** (Version control & collaboration)  

---
## Team Roles

In this project, different team members contribute according to their areas of expertise.  
Here are the key roles and responsibilities:

### 1. Backend Developer
Responsible for building and maintaining the server-side logic of the application.  
- Implements APIs and core business logic.  
- Ensures security, performance, and scalability.  
- Connects the front-end with the database.  

### 2. Frontend Developer
Focuses on the user interface and user experience.  
- Implements web pages using HTML, CSS, and JavaScript.  
- Integrates with backend APIs.  
- Ensures responsiveness and accessibility across devices.  

### 3. Database Administrator (DBA)
Manages the application’s data storage and access.  
- Designs and optimizes the database schema.  
- Ensures data integrity, security, and backups.  
- Monitors database performance.  

### 4. Project Manager
Oversees planning, execution, and delivery of the project.  
- Assigns tasks and manages timelines.  
- Facilitates team communication.  
- Ensures the project stays on track with goals.  

### 5. QA Engineer (Quality Assurance)
Responsible for testing and ensuring quality of the application.  
- Writes and runs test cases.  
- Identifies bugs and works with developers to resolve them.  
- Ensures the final product meets requirements.  

### 6. DevOps Engineer
Handles infrastructure, deployment, and automation.  
- Manages servers and cloud services.  
- Sets up CI/CD pipelines.  
- Monitors application uptime and performance.  

## Technology Stack

The AirBnB Clone project uses a combination of technologies to handle different aspects of development, from the backend to the frontend and database. Below is an overview of the stack and its purpose:

### 1. **Python**
- A high-level programming language used for backend logic and command-line tools.  
- Provides flexibility and strong libraries for building APIs and handling data.  

### 2. **Django**
- A Python-based web framework.  
- Used to build robust RESTful APIs, manage authentication, and handle backend logic efficiently.  

### 3. **PostgreSQL**
- A powerful open-source relational database.  
- Stores application data such as users, bookings, listings, and reviews.  
- Provides scalability, reliability, and strong query performance.  

### 4. **GraphQL**
- A query language for APIs.  
- Allows the frontend to request exactly the data it needs, reducing over-fetching.  
- Improves communication between frontend and backend.  

### 5. **JavaScript**
- A dynamic scripting language for client-side interactivity.  
- Powers dynamic elements of the user interface.  

### 6. **HTML & CSS**
- Core technologies for structuring and styling the frontend.  
- Ensures the application is visually appealing and user-friendly.  

### 7. **Git & GitHub**
- Version control and collaboration tools.  
- Used to track changes, manage branches, and work collaboratively as a team.  

## Database Design

The AirBnB Clone project requires a well-structured database to manage users, properties, bookings, reviews, and payments. Below is an overview of the key entities and their relationships:

### 1. **Users**
Fields:  
- `id` (Primary Key)  
- `name`  
- `email`  
- `password`  
- `phone_number`  

**Relationships:**  
- A user can have multiple properties (as a host).  
- A user can make multiple bookings.  
- A user can write multiple reviews.  

---

### 2. **Properties**
Fields:  
- `id` (Primary Key)  
- `owner_id` (Foreign Key → Users.id)  
- `title`  
- `description`  
- `location`  
- `price_per_night`  

**Relationships:**  
- A property belongs to a single user (host).  
- A property can have multiple bookings.  
- A property can receive multiple reviews.  

---

### 3. **Bookings**
Fields:  
- `id` (Primary Key)  
- `user_id` (Foreign Key → Users.id)  
- `property_id` (Foreign Key → Properties.id)  
- `start_date`  
- `end_date`  
- `status`  

**Relationships:**  
- Each booking is made by a single user.  
- Each booking is for a single property.  

---

### 4. **Reviews**
Fields:  
- `id` (Primary Key)  
- `user_id` (Foreign Key → Users.id)  
- `property_id` (Foreign Key → Properties.id)  
- `rating`  
- `comment`  
- `created_at`  

**Relationships:**  
- Each review is written by a single user.  
- Each review belongs to a single property.  

---

### 5. **Payments**
Fields:  
- `id` (Primary Key)  
- `booking_id` (Foreign Key → Bookings.id)  
- `amount`  
- `payment_date`  
- `payment_method`  

**Relationships:**  
- Each payment is linked to a single booking.  

## Feature Breakdown

The Airbnb Clone project includes several core features that mimic real-world Airbnb functionality. Below is a summary of the main features:

### 1. User Management
Allows users to create accounts, log in, and manage their profiles.  
This feature ensures secure authentication and provides a personalized experience for both guests and hosts.

### 2. Property Management
Enables hosts to list properties with details such as title, description, location, and pricing.  
Hosts can update or remove listings, and users can browse available properties.

### 3. Booking System
Allows users to book available properties for selected dates.  
The system manages booking confirmation, availability, and prevents double-booking conflicts.

### 4. Reviews & Ratings
Users can leave reviews and ratings for properties they have stayed in.  
This feedback system helps future guests make informed decisions and promotes trust between hosts and users.

### 5. Payment Integration
Handles secure payments for bookings using multiple payment methods.  
It ensures accurate transaction records and updates the booking status after payment is confirmed.

### 6. Search & Filters
Allows users to search for properties based on location, price, and availability.  
Filters improve user experience by helping users find suitable listings quickly.

## API Security

Securing backend APIs is critical to protect user data, maintain trust, and ensure safe transactions within the Airbnb Clone project. The following key security measures will be implemented:

### 1. Authentication
Users must log in with a secure account before accessing protected endpoints.  
This ensures that only verified users can access their personal data and perform actions such as booking or listing properties.

### 2. Authorization
Different user roles (guest, host, admin) will have specific permissions.  
Authorization prevents users from performing actions outside of their role, such as editing another user’s bookings or listings.

### 3. Rate Limiting
The API will limit the number of requests a user can make in a given time frame.  
This helps prevent abuse, such as brute-force login attempts, and reduces server overload.

### 4. Data Encryption
Sensitive data like passwords and payment information will be encrypted both in transit (HTTPS) and at rest.  
Encryption protects user privacy and secures financial transactions.

### 5. Input Validation
All data received by the API will be validated to prevent malicious input.  
This protects against attacks such as SQL injection or cross-site scripting (XSS).

**Importance:**  
These measures collectively ensure that user data, property listings, bookings, and payments remain secure. Strong API security protects both the users and the platform from unauthorized access, fraud, and potential breaches.
