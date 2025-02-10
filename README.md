## Task Management Server - React Fundamental Project 15

This is a simple task management server built with Express.j (using for running React Query Task Manager - React Fundamental Project 15) . It provides a RESTful API to manage tasks, including creating, updating, and deleting tasks.

**Backend Online Live:** https://task-management-server-nyfr.onrender.com

**Frontend Online Live:**

**Front-End Source Code:**

## Project Structure

```
.
├── localDataServer.js
├── package.json
├── server.js
└── tasks.json
```

- `localDataServer.js`: Main server file using for Local Storage Server that handles API requests. (Alternative Approach)
- `package.json`: Contains project metadata and dependencies.
- `server.js`: Entry point for the server (Not using Local Storage).
- `tasks.json`: JSON file to store tasks data.

## Installation

1. Clone the repository.
2. Navigate to the project directory.
3. Install the dependencies:

```sh
npm install
```

## Running the Server

To start the server, run:

```sh
npm start
```

To start the local data server, run:

```sh
npm run local-server
```

## API Endpoints

### GET /

Returns a welcome message.

**Response:**

```html
<h1>Hello From Server...</h1>
```

### GET /api/tasks

Returns the list of tasks.

**Response:**

```json
{
  "taskList": [
    {
      "id": "unique-task-id",
      "title": "Task title",
      "isDone": false
    }
  ]
}
```

### POST /api/tasks

Creates a new task.

**Request Body:**

```json
{
  "title": "Task title"
}
```

**Response:**

```json
{
  "task": {
    "id": "unique-task-id",
    "title": "Task title",
    "isDone": false
  }
}
```

### PATCH /api/tasks/:id

Updates the status of a task.

**Request Parameters:**

- `id`: The ID of the task to update.

**Request Body:**

```json
{
  "isDone": true
}
```

**Response:**

```json
{
  "msg": "task updated"
}
```

### DELETE /api/tasks/:id

Deletes a task.

**Request Parameters:**

- `id`: The ID of the task to delete.

**Response:**

```json
{
  "msg": "task removed"
}
```

## Middleware

- `cors`: Enables Cross-Origin Resource Sharing.
- `morgan`: HTTP request logger middleware for Node.js.
- `express.json()`: Parses incoming requests with JSON payloads.

## Error Handling

If a route does not exist, the server responds with a 404 status code and a message:

```text
Route does not exist
```

## Environment Variables

- `PORT`: The port on which the server will listen (default is 5000).
