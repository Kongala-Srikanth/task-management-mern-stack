# Task Management API

A **Task Management API** built with **Express.js** and **SQLite**. This API allows users to register, log in, create tasks, update tasks, delete tasks, and fetch user-specific tasks or profile information.

## Features
1. **User Management**
   - Register a new user.
   - User login with JWT authentication.
   - Fetch user profile details.

2. **Task Management**
   - Create a task with title, description, and status.
   - Update task details.
   - Delete a task.
   - Retrieve all tasks for a specific user.

3. **Authentication**
   - Secure endpoints using **JWT (JSON Web Tokens)**.

4. **Database**
   - Persistent data storage using **SQLite** with tables for users and tasks.

---

## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org) installed on your system.
- Basic understanding of REST APIs.
- SQLite database.

### Setup

## 1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <project-directory>
  ```
### 2. Install dependencies:
```bash
npm install
```
### 3. Create a .env file in the root directory with the following content:
```bash
JWT_SECRET=your_secret_key
```
### 4. Start the server:
```bash
node <file-name>.js
```
Replace <file-name> with the name of your server file.

## API Endpoints
### 1. Register New User
- Endpoint: /register
- Method: POST
- Request Body:
```bash
{
  "username": "Srikanth",
  "email": "srikanth@gmail.com",
  "password": "srikanth"
}
```
- **Response**:
```bash
{
  "message": "User Registered Successfully"
}
```
### 2. Login
- Endpoint: /login
- Method: POST
- Request Body:
```bash
{
  "email": "srikanth@gmail.com",
  "password": "srikanth"
}
```
- **Response**:
```bash
{
  "jwtToken": "your_generated_jwt_token"
}
```

## Task APIs
### 3. Create a Task
- URL: /api/tasks
- Method: POST
- Headers: Authorization: Bearer <jwt-token>
- Request Body:
```bash
{
  "title": "Sample Task",
  "description": "This is a sample task description.",
  "status": "To Do"
}
```
- **Response**:
```bash
{
  "message": "Task added successfully",
  "taskId": 1
}
```

### 4. Delete a Task
- URL: /api/tasks/:id
- Method: DELETE
- Headers: Authorization: Bearer <jwt-token>
- **Response**:
```bash
{
  "message": "Task deleted successfully"
}
```

### 5. Update a Task
- URL: /api/tasks/:id
- Method: PUT
- Headers: Authorization: Bearer <jwt-token>
- Request Body:
```bash
{
  "title": "Updated Title",
  "description": "Updated Description",
  "status": "Completed"
}
```
- **Response**:
```bash
{
  "message": "Task updated successfully"
}
```

### 6. Get All Tasks
- URL: /api/tasks
- Method: GET
- Headers: Authorization: Bearer <jwt-token>
- **Response**:
```bash
{
  /* Tasks details */
}
```

### 7. Get User Details
- URL: /api/profile
- Method: GET
- Headers: Authorization: Bearer <jwt-token>
- **Response**:
```bash
{
  /* User details */
}
```


## Dependencies
- Node.js: Server-side JavaScript runtime.
- express: Fast, unopinionated web framework
- cors: Enable Cross-Origin Resource Sharing
- SQLite: Lightweight database for data persistence.
- jsonwebtoken: Authenticate and secure API
- bcrypt: Hash passwords for secure storage
- dotenv: Manage environment variables

## Notes
- Ensure that the .env file is properly configured with the secret key.
- The SQLite database will automatically initialize tables if they don't exist.
