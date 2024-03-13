# Demo Application
The application is a simple CRUD application for managing users, built with Spring Boot and MongoDB.

## Pre-requisites
* docker
* docker-compose
* java 17 jdk

## Running the application
* Run `docker-compose up -d` to start the mongodb instance
  * The mongodb instance will be initialized with a demo database and credentials via the `mongodb-init/init.js` script
* Run `./gradlew bootRun` to start the application

## Testing the application
The integration test **[DemoServiceApplicationTests.kt](src%2Ftest%2Fkotlin%2Forg%2Fexample%2Fdemoservice%2FDemoServiceApplicationTests.kt)** runs with the help of MongoDB Testcontainers (https://testcontainers.com/).
For them to run, you need to have docker installed and running on your machine.

# API Documentation
Swagger UI is available at `http://localhost:8080/swagger-ui/index.html`

# Notes
The service is a multitenancy application. A tenant has its own customer base with its own range of customer numbers.
Tenants might be different websites, e.g., 'tipp24.de' and 'lotto24.de'.
This means customer numbers can be reused on different tenants by different customers.
