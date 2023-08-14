# Cinema app
This is a RESTful web application that mimics a movie service. Its features include buying tickets, searching for available movies for rent, checking purchase history, and user registration and verification. Moreover, the app includes role-based categorization for users.

## Project Structure
Cinema app project follows a three-tier architecture with the following structure:

* Controller: Handles incoming requests from user and admin and invokes the appropriate service methods.
* Service: Implements the business logic of the application and interacts with the DAO layer.
* DAO: Transfers requests from the service layer to the database, and executes SQL queries.
* Project also has logic of identification, authentication, authorization, filtration and encoding realized by Spring which provides additional security of user data
## User Access Endpoints
* POST: /register (create a user)
* POST: /orders/complete (create an order for the current user)
* PUT: /shopping-carts/movie-sessions (add a movie session to the shopping cart)
* GET: /orders (get order history for the current user)
* GET: /shopping-carts/by-user (get a shopping cart for the current user)
* GET: /cinema-halls (get all cinema halls)
* GET: /movies (get all movies)
* GET: /movie-sessions/available (get all available movies by date)
## Admin Access Endpoints
*   POST: /cinema-halls (create a cinema hall)
*   POST: /movies (create a movie)
*   POST: /movie-sessions (create a movie session)
*   PUT: /movie-sessions/{id} (update a movie session)
*   DELETE: /movie-sessions/{id} (delete a movie session)
*   GET: /users/by-email (find a user by email)

 All endpoints send and receive JSON data, except for the login page, which is generated by Spring Security. Almost all endpoints are secured by role-based authorization. More details can be found in the SecurityConfig class.

## Technologies used:
* Java 17
* Tomcat 9.0.75
* MySQL 8.0.22
* Maven 3.1.1
* Java Servlet 4.0.1
* Spring 5.3.20
* Spring-Web 5.3.20
* Spring-Security 5.6.10
* Hibernate 5.6.14.Final
* JDBC

## DB schema
![cinema](https://github.com/vika-trach/my-cinema-app/assets/122274162/92ad1dd0-d07c-44b7-bea6-a054441a6524)
##
1. Clone this project from GitHub
2. To deploy this project you need to install Apache Tomcat web server.
3. It's better to use 9.0.50 version. You can download it from the official Apache Tomcat website: https://tomcat.apache.org/download-90.cgi. After installation, you can set up necessary configurations and fix Tomcat by selecting the artifact to deploy taxi-service:war exploded. It's also better to remove the Application context taxi_service_war exploded to /
<img width="1034" alt="Знімок екрана 2023-08-14 о 21 21 09" src="https://github.com/vika-trach/my-cinema-app/assets/122274162/847f0bdb-16b7-4694-808c-668436579cf2">

<img width="1034" alt="Знімок екрана 2023-08-14 о 21 21 29" src="https://github.com/vika-trach/my-cinema-app/assets/122274162/5b939b69-da6e-4c69-8f8d-3031bedf755d">

5. Set up MySQL database 8 version or higher. In the db.properties file fill with the appropriate info following fields to create connection with database:
* db.driver: you database driver

* db.url: the URL of your database, including host, port, db name and additional parameters.

* db.user: your accessing username

* db.password: your accessing password

5. Install Postman to send post, put and delete requests. After this you can run your project
