# Client code
[movie-critix-client](https://github.com/Shreehar-KE/movie-critix-client)

# Movie Critix Server API

A Spring Boot based API for managing movies and their reviews, using MongoDB for data storage. This API provides endpoints for retrieving movie details, as well as creating and associating reviews with movies.

## Features
- Retrieve all movies or a single movie by its IMDb ID.
- Create reviews and associate them with specific movies.
- Built using Spring Boot and MongoDB for scalability and flexibility.
- CORS enabled for seamless integration with front-end applications.
- Environment-based configuration for secure MongoDB credentials management.

## Technologies Used
- **Spring Boot** (API, Dependency Injection, MongoDB Integration)
- **MongoDB** (NoSQL Database)
- **Lombok** (Reduces boilerplate code)
- **Spring Data MongoDB** (Data access layer for MongoDB)
- **Spring Dotenv** (Environment variable management)
- **Maven** (Dependency management)

## Installation

1. **Clone the repository:**
   ```bash
   https://github.com/Shreehar-KE/gold-imdb-server.git
   cd gold-imdb-api
   ```
2. **Configure environment variables:**
   - Store the .env file in the `src/main/resources/` directory
   ```env
      MONGO_DATABASE=your_database_name
      MONGO_USER=your_username
      MONGO_PASSWORD=your_password
      MONGO_CLUSTER=your_cluster_url
      ```
3. **Run the Application from `MoviesApplication.java` using IntelliJ IDEA**
4. **Access the API:**
- The API will be available at http://localhost:8080/api/v1/

## API Endpoints
### Movies
- **Get all movies:**
`GET /api/v1/movies`
- **Get a movie by IMDb ID:**
`GET /api/v1/movies/{imdbId}`
### Reviews
- **Create a new review:**
`POST /api/v1/reviews/`
- **Request Body:**
```json
{
  "reviewBody": "Your review text here",
  "imdbId": "Movie's IMDb ID"
}
```

## Environment Configuration
The MongoDB connection details are stored in environment variables to keep sensitive information secure. These variables in `application.properties` are loaded from a `.env` file using the `spring-dotenv` library.
```properties
spring.application.name=movies
spring.data.mongodb.database=${MONGO_DATABASE}
spring.data.mongodb.uri=mongodb+srv://${MONGO_USER}:${MONGO_PASSWORD}@${MONGO_CLUSTER}
```
