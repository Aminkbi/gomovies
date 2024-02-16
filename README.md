 **# Movie API README**

**## Overview**

This project provides a RESTful API for managing movies and user authentication. It's built with Go and utilizes a router for handling API requests.

**## Features**

- **Movie Management:**
    - List movies
    - Create movies
    - Retrieve individual movies
    - Update movies
    - Delete movies
- **User Management:**
    - Create users
- **Authentication:**
    - Generate authentication tokens
- **Health Check:**
    - Verify API availability

### Filtering Movies

The /movies endpoint supports filtering using query parameters:

    Page: Specifies the page number of results to retrieve (default: 1).
    PageSize: Specifies the number of results per page (default: 20).
    Sort: Specifies the field to sort results by (e.g., "title", "year").
        Valid values are restricted to the SortSafelist to prevent potential security issues.

**## Endpoints**

**Base URL:** `/v1`

| Method | Endpoint                       | Description                                                  |
|---------|--------------------------------|--------------------------------------------------------------|
| GET     | `/healthcheck`                  | Check API health status                                       |
| GET     | `/movies`                       | List all movies (requires `movies:read` permission)           |
| POST    | `/movies`                       | Create a new movie (requires `movies:write` permission)       |
| GET     | `/movies/:id`                   | Retrieve a specific movie by ID (requires `movies:read` permission) |
| PATCH   | `/movies/:id`                   | Update a specific movie by ID (requires `movies:write` permission) |
| DELETE  | `/movies/:id`                   | Delete a specific movie by ID (requires `movies:write` permission) |
| POST    | `/users`                        | Create a new user                                               |
| POST    | `/tokens/authentication`        | Generate an authentication token                               |

**## Permissions**

- `movies:read`: Required to access movie data
- `movies:write`: Required to create, update, or delete movies

**## Getting Started**

1. **Clone the repository:**
   ```bash
   git clone https://github.com/aminkbi/gomovies.git
   ```
2. **Install dependencies:**
   ```bash
   go get ./...
   ```
3. **Run the application:**
   ```bash
   go run main.go
   ```

**## Contributing**

We welcome contributions! Please follow these guidelines:

1. Fork the repository
2. Create a branch for your changes
3. Make your changes
4. Submit a pull request

**## License**

This project is licensed under the MIT License.


