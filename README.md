# Bajaj Finserv Health - Java Spring Boot Project

## Project Overview

This project is a Spring Boot application built for the **Bajaj Finserv Health Qualifier 1 (Java)** task. The application demonstrates:

- Sending a POST request on startup to generate a webhook.
- Solving a SQL problem based on registration number (even in this case).
- Submitting the solution to the returned webhook using a JWT token.

---

## Features

1. **Automatic Webhook Request**
   - On application startup, the app sends a POST request to the endpoint:
     ```
     https://bfhldevapigw.healthrx.co.in/hiring/generateWebhook/JAVA
     ```
   - Receives:
     - `webhook` URL
     - `accessToken` (JWT) for authorization

2. **SQL Problem Solution**
   - For even registration numbers, the app solves **Question 2**:
     - Calculates average age of employees earning more than ₹70,000 per department.
     - Generates a comma-separated list of up to 10 employee names per department.
     - Orders the output by department ID descending.
   - SQL query is implemented inside the `WebhookService.java` class.

3. **Automatic Submission**
   - The final SQL query is submitted to the webhook URL with the JWT token in the Authorization header.
   bfhproject/
├─ pom.xml
├─ mvnw
├─ mvnw.cmd
├─ src/
│ ├─ main/
│ │ ├─ java/com/example/bfhproject/
│ │ │ ├─ BfhprojectApplication.java
│ │ │ ├─ model/WebhookResponse.java
│ │ │ └─ service/WebhookService.java
│ │ └─ resources/
│ │ └─ application.properties
├─ target/
│ └─ bfhproject-0.0.1-SNAPSHOT.jar
- **Java 17**
- **Spring Boot 3.x**
- **Spring WebFlux (WebClient)**
- **H2 Database (for SQL testing)**
- **Maven** for build and dependency management

## Project Structure

