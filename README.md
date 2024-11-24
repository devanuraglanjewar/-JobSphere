#  JobSphere - Campus Recruitment Platform.

JobSphere is a backend application built to streamline the campus recruitment process. It provides RESTful APIs for managing users, students, job postings, applications, and interviews. All functionalities can be tested using Postman or similar API testing tools.

---

## Table of Contents
1. [Project Architecture](#project-architecture)
2. [Technology Stack](#technology-stack)
3. [Modules](#modules)
4. [Features](#features)
5. [Folder Structure](#folder-structure)
6. [Setup Instructions](#setup-instructions)
7. [API Documentation](#api-documentation)
8. [Contact](#contact)

---

## Project Architecture

### Layers Description
1. **Controller Layer**: Handles HTTP requests and responses.
2. **Service Layer**: Contains business logic and mediates between the controller and DAO.
3. **DAO (Data Access Object) Layer**: Interacts with the database to perform CRUD operations.

---

## Technology Stack

- **Backend Framework**: Spring Boot 
- **Database**: MySQL
- **Database Framework**: Hibernate 
- **Java Version**: JDK 17
- **Build Tool**: Maven
- **Development Environment**: Eclipse
- **API Testing Tool**: Postman

---

## Modules

1. **User Module**: Manages user authentication and role-based access.
2. **Student Module**: Handles student profiles and applications.
3. **Job Posting Module**: Enables recruiters to manage job postings.
4. **Job Application Module**: Tracks applications and their statuses.
5. **Interview Module**: Manages interview scheduling and status updates.

---

## Features

- Secure user authentication and role-based access control.
- CRUD operations for users, students, jobs, applications, and interviews.
- API-driven architecture for flexible integration with frontend or third-party tools.

---
## Folder Structure

```bash
JobSphere/
├── src/main/java/     # Contains controllers, services, and DAO classes
├── src/main/resources/
│   └── application.properties
└── README.md          # Project documentation
```
----
## Setup Instructions

### Prerequisites
- Java Development Kit 
- MySQL Database
- Maven
- Postman

### Steps to Run the Application
1. Clone the repository:
   ```bash
   git clone https://github.com/devanuraglanjewar/-JobSphere.git
   ```
2. Navigate to the project directory:
    ```bash
    cd CampusGate
    ```
3. Set up your MySQL database and update the database configurations in the application.properties file:
    ```bash
    spring.datasource.url=jdbc:mysql://localhost:3306/campus_recruit?createDatabaseIfNotExist=true
    spring.datasource.username=root
    spring.datasource.password=root
    ```
4. Install the necessary dependencies via Maven:
    ```bash
    mvn clean install
    ```

5. Run the application:
    ```bash
    mvn spring-boot:run
    ```

5. The application will start on http://localhost:8091.

## API Documentation

### Base URL
`http://localhost:8091/api`

### Endpoints

#### User Module
- **Register User**
  - `POST http://localhost:8091/api/users/register`
  - Request Body:
    ```json
    {
      "username": "Anurag",
      "password": "12345",
      "role": "ADMIN"
    }
    ```
  - Response: `201 Created`

- **Login User**
  - `POST http://localhost:8091/api/users/login`
  - Request Body:
    ```json
    {
      "username": " Anurag",
      "password": "12345"
    }
    ```
  - Response: `200 OK`

#### Student Module
- **Get All Students**
  - `GET http://localhost:8091/api/students`
  - Response: List of all students.

- **Create Student**
  - `POST http://localhost:8091/api/students`
  - Request Body:
    ```json
    {
      "name": "Anurag Lanjewar",
      "email": "anurag4lanjewar@gmail.com",
      "course": "Engineering"
    }
    ```
  - Response: `201 Created`

#### Job Posting Module
- **Get All Job Postings**
  - `GET http://localhost:8091/api/jobs`
  - Response: List of all job postings.

- **Create Job Posting**
  - `POST http://localhost:8091/api/jobs`
  - Request Body:
    ```json
    {
      "title": "Software Engineer",
      "description": "Entry-level position",
      "location": "Remote"
    }
    ```
  - Response: `201 Created`

#### Job Application Module
- **Apply for a Job**
  - `POST http://localhost:8091/api/applications`
  - Request Body:
    ```json
    {
      "studentId": 1,
      "jobId": 101
    }
    ```
  - Response: `201 Created`

- **Get Applications by Job**
  - `GET http://localhost:8091/api/applications/job/{jobId}`
  - Response: List of applications for the specified job.

#### Interview Module
- **Schedule Interview**
  - `POST http://localhost:8091/api/interviews`
  - Request Body:
    ```json
    {
      "applicationId": 1001,
      "interviewDate": "2024-11-25T10:00:00"
    }
    ```
  - Response: `201 Created`

- **Get Interviews for a Student**
  - `GET http://localhost:8091/api/interviews/student/{studentId}`
  - Response: List of scheduled interviews for the student.

---



## Contact
If you have any questions

or feedback, feel free to reach out to me at:

Email: anurag4lanjewar@gmail.com
