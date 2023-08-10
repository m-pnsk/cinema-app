# <h1 align="center">🎬 Cinema-app 🎬</h1>

## 🙌 Introduction

This project is a REST web application for a cinema. It allows users to view the schedule of movie sessions and purchase
tickets for them. The application also has a user registration system, as well as a secure section with access rights to
various resources, based on user roles. Additionally, users can obtain information about movies available at the cinema,
including their descriptions.

## 💪 Features

- register or authenticate as a user
- create and find cinema halls
- create and find movies
- create, update, delete and find available movie sessions
- creat and find shopping carts
- add tickets to shopping carts
- complete and find an orders
- find an information about user

## 💻 Technologies Used

`The following technologies are used to build the Cinema-app:`

- <img src="https://image.emojipng.com/677/13219677.jpg" width="30" alt="java-logo"/> **Java 17**: The primary programming language used for the application.
- <img src="https://w7.pngwing.com/pngs/464/18/png-transparent-mysql-database-innodb-postgresql-column-marine-mammal-electric-blue-postgresql-thumbnail.png" width="30" alt="mysql-logo"/> **MySQL 8.0.33**: The database management system used for data storage.
- <img src="https://avatars.githubusercontent.com/u/348262?s=280&v=4" width="30" alt="hibernate-logo"/> **Hibernate 5.6.14**: The ORM framework for mapping an object-oriented domain model to a relational database and vice versa.
- <img src="https://cdn.fs.teachablecdn.com/L2rtxPaRxa4am1VtNegg" width="30" alt="maven-logo"/> **Maven 4.0.0**: It is a build automation tool.
- <img src="https://img.icons8.com/color/100000/000000/tomcat.png" width="30" alt="tomcat-logo"/> **Tomcat 9.0.76**: It is a Java web application server.
- <img src="https://media.trustradius.com/product-logos/9B/8G/IMJEF6VWC74S.PNG" width="30" alt="spring-logo"/> **Spring**: A powerful framework that provides essential features for building web applications;
    - Core 5.3.20
    - Web Mvc 5.3.20
    - Security 5.6.10

## 🔧Structure

#### Project has N-Tier Architecture:

| Layer                            | Assignment                                                                                                                                       |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| Controllers (Presentation layer) | Receives requests from the client, transmits them to the service layer, and returns JSON in response.                                            |
| Services (Application layer)     | Receives requests from the controller layer, transmits them to the DAO layer, <br/>receives a response from the DAO, and executes business logic |
| DAO (Data access layer)          | Receives requests from the service layer, transfers them to the database, and executes SQL queries                                               |

#### ⚙️ Package Structure

- config - stores Spring configuration
- controller - contains controllers for endpoints
- dao - data access layer (repository) that calls CRUD methods in the database
- dto - wrapper for model objects to unify the requests and responses in controllers
- lib - contains email and password validators with its annotations
- model - contains models for the database
- service - contains services that call repositories, executes business logic
- mapper - converts model objects to DTO objects

## 💾 Hibernate entities UML diagram:

![DatabaseSchema](Schema_Cinema.png)

## 🔗 API Endpoints

`The Cinema-app provides the following API endpoints:`

| **HTTP method** | **Endpoint**                   | **Role**   | **Function**                                               |
|:----------------|:-------------------------------|------------|:-----------------------------------------------------------|
| POST            | /register                      | ALL        | Register a new user.                                       |
| POST            | /login                         | ALL        | Create a session with an authenticated user                |
| POST            | /cinema-halls                  | ADMIN      | Create a cinema hall                                       |
| GET             | /cinema-halls                  | USER/ADMIN | Get all cinema halls                                       |
| POST            | /movies                        | ADMIN      | Create a movie                                             |
| GET             | /movies                        | USER/ADMIN | Get all movies                                             |
| POST            | /movie-sessions                | ADMIN      | Create a movie session                                     |
| GET             | /movie-sessions/available      | USER/ADMIN | Get all available screenings of a particular movie by date |
| PUT             | /movie-sessions/{id}           | ADMIN      | Update a movie session                                     |
| DELETE          | /movie-sessions/{id}           | ADMIN      | Delete a movie session                                     |
| POST            | /orders/complete               | USER       | Create an order for the current user                       |
| GET             | /orders                        | USER       | Get order history for the current user                     |
| PUT             | /shopping-carts/movie-sessions | USER       | Add a movie session to the current user's shopping cart    |
| GET             | /shopping-carts/by-user        | USER       | Get a shopping cart for the current user                   |
| GET             | /users/by-email                | ADMIN      | Find a user by email                                       |

## 🚀 Getting Started

`Before running the Cinema-app, ensure you have the following installed:`

- <img src="https://image.emojipng.com/677/13219677.jpg" width="30" alt="java-logo"/> Java Development Kit (JDK)
- <img src="https://cdn.fs.teachablecdn.com/L2rtxPaRxa4am1VtNegg" width="30" alt="maven-logo"/> Maven
- <img src="https://w7.pngwing.com/pngs/464/18/png-transparent-mysql-database-innodb-postgresql-column-marine-mammal-electric-blue-postgresql-thumbnail.png" width="30" alt="mysql-logo"/> MySQL

`Follow the steps below to launch this project:`

1. Clone the repository from GitHub and navigate to the project directory.
2. Change the settings in the `resources/db.properties` file to your personal ones.
    ```
    db.driver=YOUR_DRIVER
    db.url=YOUR_DATABASE_URL
    db.user=YOUR_USERNAME
    db.password=YOUR_PASSWORD
    ```
3. Set up the configuration for Tomcat.
4. Run the project
5. The application should now be running at `http://localhost:8080`.

NOTE: If you want to log in as ADMIN use following credentials: login - `mate@gmail.ua`, password - `admin123` 