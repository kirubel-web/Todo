# Todo API

The Todo API is a Django REST Framework project that provides endpoints for managing Todo items. It allows users to create, retrieve, update, and delete Todo items.

## Installation

1. Clone the repository:

   ````bash
   git clone <repository-url>
   ```

2. Change into the project directory:

   ````bash
   cd todo-api
   ```

3. Create a virtual environment:

   ````bash
   python -m venv env
   ```

4. Activate the virtual environment:

   - On macOS and Linux:

     ```bash
     source env/bin/activate
     ```

   - On Windows:

     ```bash
     .\env\Scripts\activate
     ```

5. Install the required dependencies:

   ````bash
   pip install -r requirements.txt
   ```

6. Run database migrations:

   ````bash
   python manage.py migrate
   ```

7. Start the development server:

   ````bash
   python manage.py runserver
   ```

   The API will be available at `http://localhost:8000/`.
   If neccessary use the username:admin & password:123456 for admin interface.

## API Endpoints

### List Todos

- **URL:** `/api/todos/`
- **Method:** GET
- **Description:** Get a list of all Todo items.
- **Response:**
  - Status Code: 200 (OK)
  - Body:

    ```json
    [
      {
        "id": 1,
        "text": "Finish homework",
        "created_at": "2023-10-24T12:00:00Z"
      },
      {
        "id": 2,
        "text": "Buy groceries",
        "created_at": "2023-10-23T18:30:00Z"
      },
      // ...
    ]
    ```

### Retrieve Todo

- **URL:** `/api/todos/{id}/`
- **Method:** GET
- **Description:** Get details of a specific Todo item.
- **Response:**
  - Status Code: 200 (OK)
  - Body:

    ```json
    {
      "id": 1,
      "text": "Finish homework",
      "created_at": "2023-10-24T12:00:00Z"
    }
    ```
comming soon >.....

### Create Todo

- **URL:** `/api/todos/`
- **Method:** POST
- **Description:** Create a new Todo item.
- **Request Body:**
  - Body:

    ```json
    {
      "text": "New task"
    }
    ```
- **Response:**
  - Status Code: 201 (Created)
  - Body:

    ```json
    {
      "id": 3,
      "text": "New task",
      "created_at": "2023-10-24T15:30:00Z"
    }
    ```

### Update Todo

- **URL:** `/api/todos/{id}/`
- **Method:** PUT
- **Description:** Update a specific Todo item.
- **Request Body:**
  - Body:

    ```json
    {
      "text": "Updated task"
    }
    ```
- **Response:**
  - Status Code: 200 (OK)
  - Body:

    ```json
    {
      "id": 3,
      "text": "Updated task",
      "created_at": "2023-10-24T15:30:00Z"
    }
    ```

### Delete Todo

- **URL:** `/api/todos/{id}/`
- **Method:** DELETE
- **Description:** Delete a specific Todo item.
- **Response:**
  - Status Code: 204 (No Content)

## Error Handling

The API handles various error scenarios and returns appropriate status codes and error messages in the response body.

- **400 (Bad Request):** Returned when the request is invalid or missing required parameters.
- **404 (Not Found):** Returned when a specific Todo item is not found.
- **500 (Internal Server Error):** Returned when an unexpected server error occurs.

## Authentication and Authorization

The Todo API does not currently require authentication or authorization. It allows public access to all endpoints. If you want to add authentication or restrict access to certain endpoints, you can configure it using Django REST Framework's authentication and permission classes.

## Contribute

Contributions are welcome! If you find any issues or want to add new features, please submit an issue or pull request on the GitHub repository.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use, modify, and distribute the code.