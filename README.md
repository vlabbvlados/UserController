# Simple User Management REST API

A simple REST API for managing users, built with Spring Boot. This project is a foundational example of a backend service with full CRUD functionality and persistent data storage.

## Technologies Used

* Java 17
* Spring Boot 3.x
* Spring Data JPA
* PostgreSQL
* Maven

## API Endpoints

This API provides endpoints to manage users.

### 1. Get All Users

* **Method:** `GET`
* **URL:** `/users`
* **Description:** Retrieves a list of all users.
* **Success Response:**
    * **Code:** `200 OK`
    * **Content:** 
    ```json
        [
            {
                "id": 1,
                "name": "Alex"
            },
            {
                "id": 2,
                "name": "Maria"
            }
        ]
    ```

### 2. Get User by ID

* **Method:** `GET`
* **URL:** `/users/{id}`
* **Description:** Retrieves a single user by their unique ID.
* **Success Response:**
    * **Code:** `200 OK`
    * **Content:** 
    	```json
        {
            "id": 1,
            "name": "Alex"
        }
       ```
* **Error Response:**
    * **Code:** `404 Not Found`
    * **Content:** 
    	```json
        {
            "error": "User not found with id: 999"
        }
    	```

### 3. Create a New User

* **Method:** `POST`
* **URL:** `/users`
* **Description:** Creates a new user.
* **Request Body:**
    	```json
    {
        "name": "Alex"
    }
		```
* **Success Response:**
    * **Code:** `200 OK` (or `201 Created` - both are common)
* **Error Response (Validation):**
    * **Code:** `400 Bad Request`
    * **Content:** 
    	```json
        {
            "name": "User name cannot be blank"
        }
    	```

### 4. Update an Existing User

* **Method:** `PUT`
* **URL:** `/users/{id}`
* **Description:** Updates the name of an existing user.
* **Request Body:**
    	```json
    {
        "name": "Alexander"
    }
    	```
* **Success Response:**
    * **Code:** `200 OK`

### 5. Delete a User

* **Method:** `DELETE`
* **URL:** `/users/{id}`
* **Description:** Deletes a user by their unique ID.
* **Success Response:**
    * **Code:** `200 OK` (or `204 No Content`)