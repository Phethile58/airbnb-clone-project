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
