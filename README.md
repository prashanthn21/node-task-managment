Task Manager API
A simple RESTful Task Manager API built with Node.js, Express, and MongoDB.
Features
- Create, Read, Update, and Delete tasks
- Each task has a title, description, completed status, and due date
- Error handling middleware included
- MongoDB connection using Mongoose
Technologies Used
- Node.js
- Express
- MongoDB & Mongoose
- dotenv for environment variables
- CORS for handling cross-origin requests
Folder Structure
.
??? models
? ??? Task.js # Mongoose schema for Task
??? routes
? ??? tasks.js # API routes for CRUD operations
??? server.js # Entry point of the application
??? .env # Environment variables (MONGO_URI, PORT)
Getting Started
1. Clone the repository:
 git clone https://github.com/yourusername/task-manager-api.git
 cd task-manager-api
2. Install dependencies:
 npm install
3. Create a `.env` file and add your MongoDB URI and PORT:
 MONGO_URI=your_mongo_connection_string
 PORT=5000
4. Start the server:
 npm start
API Endpoints
- `POST /api/tasks` - Create a new task
- 
- `GET /api/tasks` - Retrieve all tasks
- `GET /api/tasks/:id` - Retrieve a task by ID
- `PUT /api/tasks/:id` - Update a task by ID
- `DELETE /api/tasks/:id` - Delete a task by ID

API Endpoints
1. Create a Task
Route: POST /api/tasks

Request Body:

json
Copy
Edit
{
  "title": "Task Title",
  "description": "Task description",
  "completed": false
}
Response:

json
Copy
Edit
{
  "_id": "task-id",
  "title": "Task Title",
  "description": "Task description",
  "completed": false,
  "createdAt": "timestamp",
  "updatedAt": "timestamp"
}
2. Get All Tasks
Route: GET /api/tasks

Response:

json
Copy
Edit
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
3. Get a Task by ID
Route: GET /api/tasks/:id

Response:

json
Copy
Edit
{
  "_id": "task-id",
  "title": "Task Title",
  "description": "Task description",
  "completed": false,
  "createdAt": "timestamp",
  "updatedAt": "timestamp"
}
Error Response (if task not found):

json
Copy
Edit
{
  "error": "Task not found"
}
4. Update a Task
Route: PUT /api/tasks/:id

Request Body:

json
Copy
Edit
{
  "title": "Updated Task Title",
  "description": "Updated Task description",
  "completed": true
}
Response:

json
Copy
Edit
{
  "_id": "task-id",
  "title": "Updated Task Title",
  "description": "Updated Task description",
  "completed": true,
  "createdAt": "timestamp",
  "updatedAt": "timestamp"
}
5. Delete a Task
Route: DELETE /api/tasks/:id

Response:

json
Copy
Edit
{
  "message": "Task deleted successfully"
}
License
This project is licensed under the MIT License.
