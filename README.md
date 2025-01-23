## API Overview

The MoviesDatabase API is a comprehensive resource for accessing data about movies, TV shows, actors, and more. It provides developers with tools to search for titles, retrieve detailed movie information, explore trending content, and discover genres. This API is ideal for building applications that need rich movie-related data.

## API Version

Version 3

## Available Endpoints

These are the main endpoints provided by the MoviesDatabase API:
- GET /movies: Search for movies based on specific keywords or filters.
- GET /movies/{id}: Retrieve detailed information for a specific movie by its unique ID.
- GET /trending: Access a list of trending movies and TV shows.
- GET /genres: Fetch a catalog of all available movie genres.
- GET /actors/{id}: Get information about a specific actor using their ID.

## Request and Response Format
 - Example Request:
    GET /movies?search=Inception HTTP/1.1
    Host: api.moviesdatabase.com
    Authorization: API_KEY

 - Example Response:
    {
  "status": "success",
  "data": {
    "id": "12345",
    "title": "White house down",
    "release_date": "2015-07-16",
    "genres": ["Action", "Thriller"],
    "rating": 7.8
  }
}

## Authentication
 To use the API TMDB, these are the steps to follow:
    1- Sign Up: Create an account on the MoviesDatabase API platform.
    2- Obtain API Key: Get your unique API key from the dashboard.
    3- Add API Key to Requests: Include the key in the Authorization header

## Error Handling
 TMDB provides many error messages to help troubleshoot issues, below are some of the common ones:
    - 401 Unauthorized: Indicates an invalid or missing API key.
    - 404 Not Found: The requested resource could not be found.
    - 429 Too Many Requests: Your request quota has been exceeded.

 to handle these eroors we should:
  - Check HTTP status codes before processing responses.
  - Log errors for debugging purposes.
  - Use retry mechanisms for rate-limiting errors, with delays between retries.

## Usage Limits and Best Practices
- Rate Limit: Maximum of 100 requests per minute. Exceeding this results in a 429 Too Many Requests error.
- Optimize Requests: Use filters to fetch only the data you need.
- Cache Data: Store frequent responses locally to reduce API calls.
- Secure API Key: Keep your API key private and avoid exposing it in public code.