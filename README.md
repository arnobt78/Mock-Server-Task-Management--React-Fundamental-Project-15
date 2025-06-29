# Task Management Mock Server  
*A React Fundamental Project (Project 15)*

---

## Project Summary

This project provides a simple **task management server** built with **Node.js** and **Express.js**. It is designed as a backend mock server for task management applications, especially for learning and practicing RESTful API usage with frontend frameworks like React. The server supports full CRUD (Create, Read, Update, Delete) operations on tasks, making it ideal for **learning full-stack development**, API interaction, and building modern React apps with real-world API experience.

This backend is paired with a React frontend.  
- **Backend Live:** [https://task-management-server-nyfr.onrender.com](https://task-management-server-nyfr.onrender.com)
- **Frontend Live:** [https://react-query-task-manager-arnob.netlify.app/](https://react-query-task-manager-arnob.netlify.app/)
- **Frontend Source Code:** [React-Query-Task-Manager--React-Fundamental-Project-15](https://github.com/arnobt78/React-Query-Task-Manager--React-Fundamental-Project-15)

---

## Table of Contents

- [Project Summary](#project-summary)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Running the Server](#running-the-server)
- [API Endpoints](#api-endpoints)
    - [GET /](#get-)
    - [GET /api/tasks](#get-apitasks)
    - [POST /api/tasks](#post-apitasks)
    - [PATCH /api/tasks/:id](#patch-apitasksid)
    - [DELETE /api/tasks/:id](#delete-apitasksid)
- [Middleware](#middleware)
- [Error Handling](#error-handling)
- [Environment Variables](#environment-variables)
- [Keywords & Technologies](#keywords--technologies)
- [Learning & Teaching Notes](#learning--teaching-notes)
- [Project Walkthrough](#project-walkthrough)
- [Example Scripts & Usage](#example-scripts--usage)
- [Conclusion](#conclusion)

---

## Features

- **Mock RESTful API** – Simulates backend for task management (To-Do app) projects.
- **CRUD Operations** – Supports creating, reading, updating, and deleting tasks.
- **Local and Remote Data Storage** – Supports both file-based JSON storage and local in-memory storage for flexibility in development.
- **Middleware Integration** – Includes CORS, logging, and JSON parsing.
- **Easy Integration** – Ready to use with any frontend (React, Angular, Vue, etc).
- **Educational Focus** – Perfect for teaching API consumption, state management, and backend concepts to beginners.

---

## Project Structure

```
.
├── localDataServer.js   # Alternative entry using local (in-memory) storage
├── package.json         # Metadata, dependencies, and scripts
├── server.js            # Main server entry, uses file-based storage
└── tasks.json           # JSON file that stores all tasks
```

- **server.js**: Main Express server (default entry) using file-based storage.
- **localDataServer.js**: Alternative server using in-memory/local storage (no files).
- **tasks.json**: Persistent JSON file for storing task data.
- **package.json**: Project config and dependencies.

---

## Installation & Setup

1. **Clone the repository:**
   ```sh
   git clone https://github.com/arnobt78/Mock-Server-Task-Management--React-Fundamental-Project-15.git
   cd Mock-Server-Task-Management--React-Fundamental-Project-15
   ```

2. **Install dependencies:**
   ```sh
   npm install
   ```

---

## Running the Server

- **Default (file-based) server:**
  ```sh
  npm start
  ```
  Runs `server.js` using tasks.json for persistent data.

- **Local (in-memory) server:**
  ```sh
  npm run local-server
  ```
  Runs `localDataServer.js` – all data is lost on restart.

---

## API Endpoints

### GET /

Returns a welcome message.

**Response:**
```html
<h1>Hello From Server...</h1>
```

---

### GET /api/tasks

Returns a list of all tasks.

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

---

### POST /api/tasks

Create a new task.

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

---

### PATCH /api/tasks/:id

Update the completion status of a task.

**Request Parameters:**
- `id`: Task ID to update.

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

---

### DELETE /api/tasks/:id

Delete a task by its ID.

**Request Parameters:**
- `id`: Task ID to delete.

**Response:**
```json
{
  "msg": "task removed"
}
```

---

## Middleware

- **cors**: Enables Cross-Origin Resource Sharing (useful for running frontend locally).
- **morgan**: HTTP request logger for debugging and monitoring.
- **express.json()**: Parses incoming JSON requests.

---

## Error Handling

If a route does not exist, the server responds with:

**Status**: 404  
**Body:**
```text
Route does not exist
```

---

## Environment Variables

- `PORT`: The port the server runs on (default: 5000).

---

## Keywords & Technologies

- **JavaScript**
- **Node.js**
- **Express.js**
- **REST API**
- **CRUD**
- **JSON**
- **CORS**
- **morgan**
- **React** (frontend client)
- **React Query** (frontend for data fetching)
- **Learning Backend**
- **Mock Server**

---

## Learning & Teaching Notes

This project is ideal for:
- **Learning RESTful APIs**: Practice GET/POST/PATCH/DELETE with real HTTP requests.
- **Frontend Integration**: Use with the paired React frontend for full-stack experience.
- **Testing State Management**: Integrate with React Query, Redux, or Context API.
- **Understanding Server Concepts**: Middleware, routing, error handling, environment configuration.

---

## Project Walkthrough

1. **Start the server** (see instructions above).
2. **Connect a frontend client** (e.g., the provided React app, or Postman).
3. **Add new tasks** via `POST /api/tasks`.
4. **View tasks** via `GET /api/tasks`.
5. **Mark tasks as done/undone** via `PATCH /api/tasks/:id`.
6. **Delete tasks** via `DELETE /api/tasks/:id`.
7. **Experiment**: Try different API calls, break things, and see how the server responds!

---

## Example Scripts & Usage

**Add a task (curl):**
```sh
curl -X POST http://localhost:5000/api/tasks -H "Content-Type: application/json" -d '{"title":"Learn Express"}'
```

**Toggle a task's done state:**
```sh
curl -X PATCH http://localhost:5000/api/tasks/<task_id> -H "Content-Type: application/json" -d '{"isDone":true}'
```

**Delete a task:**
```sh
curl -X DELETE http://localhost:5000/api/tasks/<task_id>
```

---

## Conclusion

This backend mock server is a perfect tool for learning and teaching **full-stack JavaScript development**. It provides a realistic but simple backend for practicing API consumption with frontend frameworks like React. Use it as a base for further projects, hack on it, or pair it with the frontend for a complete learning playground.

*Happy coding and learning!*

---
