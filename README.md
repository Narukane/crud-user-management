# CRUD User Project

This project provides CRUD (Create, Read, Update, Delete) operations for managing user entities. It supports two roles: admin and user. Admins have full access to CRUD operations, while users can only read user data.

## Features

- User CRUD operations:
  - Create a new user
  - Read user details
  - Update user information
  - Delete a user
- Role-based access control:
  - Admin role: Full access to all CRUD operations
  - User role: Read-only access to user data
- Token-based authentication:
  - Access tokens are used for authentication
  - Tokens expire after 1 hour
- Environment variables:
  - A secret key is required for accessing the application
  - Use the `.env` file to store the secret key
- `generate-key.js` script:
  - A script to generate a secret key for development purposes

## Project Structure

- middleware/
    - authenticateUser.js
- models/
    - User.js
- routes/
    - auth/
        - authRoutes.js
    - user/
        - userRoutes.js
- utils/
    - generate-key.js
- .env
- server.js

- `middleware/`: Contains middleware functions used in the application.
  - `authenticateUser.js`: Middleware for user authentication.
- `models/`: Contains the database models.
  - `User.js`: Model for the User entity.
- `routes/`: Contains the route handlers for different parts of the API.
  - `auth/`: Handles authentication-related routes.
    - `authRoutes.js`: Defines routes for user authentication (login, register, etc.).
  - `user/`: Handles user-related routes.
    - `userRoutes.js`: Defines routes for CRUD operations on user entities.
- `utils/`: Contains utility scripts and functions.
  - `generate-key.js`: A script to generate a secret key.
- `.env`: Environment variables file (to store configuration variables, including the secret key).
- `server.js`: Entry point of the application, where the server is initialized and routes are connected.

## Getting Started

To set up the project, follow these steps:

1. Clone the repository to your local machine.
2. Install the project dependencies by running `npm install`.
3. Generate a secret key by executing `node generate-key.js`. This will generate a key and update the `.env` file with the new value.
4. Configure the database connection in the `.env` file.
5. Run the application using `node server.js` or `npm start`.

## Usage

Once the project is running, you can access the following endpoints:

- `POST /auth/register` - Create a new User.
- `POST /auth/login` - Login to get token.

- `GET /users` - Retrieve a list of all users (admin-only).
- `GET /users/:id` - Retrieve a specific user by ID (admin-only and user).
- `PUT /users/:id` - Update a specific user by ID (admin-only).
- `DELETE /users/:id` - Delete a specific user by ID (admin-only).

To perform any operation, include the access token in the request headers as follows:

Authorization: Bearer <access_token>

## Conclusion

The User CRUD project provides a secure and role-based system for managing user data. With the ability to authenticate using access tokens, limit user permissions based on roles, and a secret key for token generation, the project ensures data integrity and access control.

Feel free to customize the project according to your specific requirements and extend it further as needed.
