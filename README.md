# my-project
# Citizens Bank Mortgage Application

## Overview
This repository contains the source code for the Citizens Bank Mortgage Application, a Java-based web application designed to manage mortgage applications, loan processing, and customer interactions. Built with Spring Boot, it provides secure, scalable, and efficient handling of mortgage-related operations.

## Features
- **Loan Application Management**: Submit, track, and update mortgage applications.
- **Customer Portal**: User-friendly interface for customers to view loan status and documents.
- **Payment Processing**: Integration with payment gateways for mortgage payments.
- **Credit Assessment**: Automated credit score evaluation and eligibility checks.
- **Document Verification**: Upload and validate documents like pay stubs and bank statements.
- **Admin Dashboard**: Tools for loan officers to review applications and manage workflows.

## Technologies Used
- **Java**: Version 17 (LTS)
- **Spring Boot**: 3.2.x for backend framework
- **Maven**: Dependency management and build tool
- **MySQL**: Database for storing customer and loan data
- **Spring Security**: Authentication and authorization
- **Thymeleaf**: Server-side templating for UI
- **REST APIs**: For integration with frontend and external services
- **JUnit 5**: Unit and integration testing
- **Docker**: Containerization for deployment

## Prerequisites
Before setting up the project, ensure you have the following installed:
- Java Development Kit (JDK) 17
- Maven 3.8.x or higher
- MySQL 8.0 or higher
- Docker (optional, for containerized deployment)
- Git

## Setup Instructions
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/citizens-mortgage-app.git
   cd citizens-mortgage-app
   ```

2. **Configure Database**:
   - Create a MySQL database named `citizens_mortgage`.
   - Update the database configuration in `src/main/resources/application.properties`:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/citizens_mortgage
     spring.datasource.username=your-username
     spring.datasource.password=your-password
     spring.jpa.hibernate.ddl-auto=update
     ```

3. **Install Dependencies**:
   ```bash
   mvn clean install
   ```

4. **Run the Application**:
   ```bash
   mvn spring-boot:run
   ```
   - The application will start on `http://localhost:8080`.

5. **Access the Application**:
   - Customer Portal: `http://localhost:8080/customer`
   - Admin Dashboard: `http://localhost:8080/admin`
   - Default credentials (for testing):
     - Admin: `admin@citizens.com` / `password`
     - Customer: `test@citizens.com` / `password`

## Building and Testing
- **Compile the Project**:
  ```bash
  mvn compile
  ```

- **Run Tests**:
  ```bash
  mvn test
  ```
  - Tests include unit tests for service layers and integration tests for REST APIs.

- **Package the Application**:
  ```bash
  mvn package
  ```
  - This generates a JAR file in the `target/` directory.

## Deployment
### Local Deployment
- Run the packaged JAR:
  ```bash
  java -jar target/citizens-mortgage-app-1.0.0.jar
  ```

### Docker Deployment
1. Build the Docker image:
   ```bash
   docker build -t citizens-mortgage-app .
   ```

2. Run the container:
   ```bash
   docker run -p 8080:8080 --env-file .env citizens-mortgage-app
   ```
   - Ensure `.env` contains database credentials and other environment variables.

## Project Structure
```
citizens-mortgage-app/
├── src/
│   ├── main/
│   │   ├── java/com/citizens/mortgage/
│   │
