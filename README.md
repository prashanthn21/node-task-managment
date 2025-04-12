Here is the rewritten version of the README:

---

# Task Manager API

A simple RESTful Task Manager API built with Node.js, Express, and MongoDB.

## Features
- Perform Create, Read, Update, and Delete (CRUD) operations on tasks.
- Each task includes a title, description, completed status, and due date.
- Includes error-handling middleware.
- Utilizes Mongoose for MongoDB integration.

## Technologies Used
- Node.js
- Express
- MongoDB & Mongoose
- dotenv for environment variables
- CORS for cross-origin request handling

## Folder Structure
```
.
├── models
│   └── Task.js     # Mongoose schema for Task
├── routes
│   └── tasks.js    # API routes for CRUD operations
├── server.js       # Entry point of the application
└── .env            # Environment variables (MONGO_URI, PORT)
```

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/task-manager-api.git
   cd task-manager-api
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file and add your MongoDB URI and PORT:
   ```env
   MONGO_URI=your_mongo_connection_string
   PORT=5000
   ```

4. Start the server:
   ```bash
   npm start
   ```

## API Endpoints
### 1. Create a Task
- **Route:** `POST /api/tasks`
- **Request Body:**
   ```json
   {
     "title": "Task Title",
     "description": "Task description",
     "completed": false
   }
   ```
- **Response:**
   ```json
   {
     "_id": "task-id",
     "title": "Task Title",
     "description": "Task description",
     "completed": false,
     "createdAt": "timestamp",
     "updatedAt": "timestamp"
   }
   ```

### 2. Get All Tasks
- **Route:** `GET /api/tasks`
- **Response:**
   ```json
   [
     {
       "_id": "task-id",
       "title": "Task Title",
       "description": "Task description",
       "completed": false,
       "createdAt": "timestamp",
       "updatedAt": "timestamp"
     }
   ]
   ```

### 3. Get a Task by ID
- **Route:** `GET /api/tasks/:id`
- **Response:**
   ```json
   {
     "_id": "task-id",
     "title": "Task Title",
     "description": "Task description",
     "completed": false,
     "createdAt": "timestamp",
     "updatedAt": "timestamp"
   }
   ```
- **Error Response (if task not found):**
   ```json
   {
     "error": "Task not found"
   }
   ```

### 4. Update a Task
- **Route:** `PUT /api/tasks/:id`
- **Request Body:**
   ```json
   {
     "title": "Updated Task Title",
     "description": "Updated Task description",
     "completed": true
   }
   ```
- **Response:**
   ```json
   {
     "_id": "task-id",
     "title": "Updated Task Title",
     "description": "Updated Task description",
     "completed": true,
     "createdAt": "timestamp",
     "updatedAt": "timestamp"
   }
   ```

### 5. Delete a Task
- **Route:** `DELETE /api/tasks/:id`
- **Response:**
   ```json
   {
     "message": "Task deleted successfully"
   }
   ```

