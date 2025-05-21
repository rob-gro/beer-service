# Beer Service

Beer Service is a Spring Boot microservice dedicated to beer inventory management. The application provides a specialized REST API for beer-related operations within the brewery ecosystem, with JPA persistence, input validation, exception handling, and pagination support.

## 🚀 Features

### 🍺 Beer Management
- **Get Beer**: Retrieve beer details by ID
- **Create Beer**: Add new beers to the inventory
- **Update Beer**: Modify existing beer information
- **Pagination Support**: Efficient handling of large beer catalogs

### 🔧 Technical Features
- **JPA Persistence**: Database storage for beer inventory
- **Input Validation**: Bean validation for request data integrity
- **Error Handling**: Global exception handling with meaningful HTTP responses
- **Bootstrapping**: Initial data loading for development environments

## 🛠 Technologies

- **Framework**: Spring Boot
- **Persistence**: Spring Data JPA with Hibernate
- **Database**: H2 Database (development) / MySQL (production)
- **Architecture**: RESTful API
- **Input Validation**: Spring Validation
- **Development**: Lombok for reduced boilerplate
- **ID Generation**: UUID for distributed systems compatibility

## 🗂 Project Structure

### Main Components

#### Domain Layer
- **Entities**:
    - `Beer.java` - JPA entity representing a beer in the database

#### Repository Layer
- **Data Access**:
    - `BeerRepository.java` - Spring Data repository for beer operations

#### Web Layer
- **API Controllers**:
    - `BeerController.java` - REST controller for beer operations
    - `MvcExceptionHandler.java` - Global exception handling for the API

#### Model Layer
- **Data Transfer Objects**:
    - `BeerDto.java` - DTO for beer information
    - `BeerPagedList.java` - Paginated list of beer DTOs
    - `BeerStyleEnum.java` - Enumeration of beer styles

#### Bootstrap
- **Data Initialization**:
    - `BeerLoader.java` - Initial data loader for development environment

## 📋 Beer Properties

Beer entities store the following information:
- **ID**: Unique UUID identifier
- **Version**: Optimistic locking version
- **Created Date**: Timestamp of creation
- **Last Modified Date**: Timestamp of last update
- **Beer Name**: Name of the beer
- **Beer Style**: Style/type of beer
- **UPC**: Universal Product Code (unique)
- **Price**: Beer price
- **Min On Hand**: Minimum inventory level
- **Quantity to Brew**: Quantity for production batches

## 📡 API Endpoints

- `GET /api/v1/beer/{beerId}` - Get beer by ID
- `POST /api/v1/beer` - Create new beer
- `PUT /api/v1/beer/{beerId}` - Update beer

## 🔄 Microservice Architecture

This service is part of a brewery microservice architecture:
- **Brewery**: Core API for brewery data management
- **Brewery Client**: Client library for consuming the brewery API
- **Beer Service** (this service): Specialized service for beer inventory management

## 🚀 Deployment

To run the application:
1. Ensure you have Java 11+ installed
2. Build with Maven: `mvn clean package`
3. Run the JAR file: `java -jar target/beer-service-0.0.1-SNAPSHOT.jar`
4. The service will be available at `http://localhost:8080`

## 🔐 Security & Validation

- **Input Validation**: Required fields for beer DTOs
- **Exception Handling**: Proper error responses for validation failures
- **Version Control**: Optimistic locking for concurrent updates
- **Audit Trail**: Creation and modification timestamps

---

Beer Service represents a modern approach to beer inventory management, offering a specialized microservice focused on beer-related operations. The system provides a comprehensive solution for businesses seeking an effective way to manage their beer products within a distributed architecture.
