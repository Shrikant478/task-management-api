Below is a step-by-step guide written in a way that you can directly use for your GitHub `README.md` file. It includes instructions to set up, run, and test the API using Postman.

---

# Task Management API

This is a simple Task Management API built with Node.js, Express, and MongoDB to perform CRUD operations on tasks. Follow the steps below to set up, run, and test the API.

---

## Features
- Create tasks
- Retrieve all tasks or by ID
- Update tasks
- Delete tasks

---

## Prerequisites
1. Node.js (v14 or later) - [Download and Install Node.js](https://nodejs.org/)
2. MongoDB - Install MongoDB locally or use a cloud MongoDB provider like [MongoDB Atlas](https://www.mongodb.com/atlas/database).

---

## Getting Started

### 1. Clone the Repository
```bash
git clone <repository-url>
cd task-manager-api
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Set Up Environment Variables
1. Create a `.env` file in the root directory:
   ```bash
   touch .env
   ```
2. Add the following variables to the `.env` file:
   ```
   MONGO_URI=mongodb://localhost:27017/taskmanager
   PORT=3000
   ```
   Replace `MONGO_URI` with your actual MongoDB connection string if using a cloud database.

### 4. Start MongoDB
- If running MongoDB locally, ensure it is started:
  ```bash
  mongod
  ```

### 5. Start the Server
To start the API server:
```bash
npm run dev
```
The server will run on `http://localhost:3000` by default.

---

## API Endpoints

The following endpoints are available:

### 1. Create a Task
- Endpoint: `POST /tasks`
- Body (JSON):
  ```json
  {
    "title": "Task Title",
    "description": "Task Description",
    "status": "Pending"
  }
  ```
- Response: The created task.

---

### 2. Get All Tasks
- Endpoint: `GET /tasks`
- Response: A list of all tasks.

---

### 3. Get Task by ID**
- Endpoint: `GET /tasks/:id`
- Response: The task with the specified ID.

---

### 4. Update a Task
- Endpoint: `PUT /tasks/:id`
- Body (JSON):
  ```json
  {
    "title": "Updated Title",
    "description": "Updated Description",
    "status": "In Progress"
  }
  ```
- Response: The updated task.

---

### 5. Delete a Task
- Endpoint: `DELETE /tasks/:id`
- Response: A success message.

---

## Testing with Postman

1. Install Postman: [Download Postman](https://www.postman.com/downloads/).
2. Create a New Request:
   - Open Postman and click `+` to create a new request.
3. Test API Endpoints:
   - POST `/tasks`:
     - Select `POST` method and enter `http://localhost:3000/tasks` in the URL field.
     - Go to the `Body` tab and select `raw` and `JSON`.
     - Enter the JSON body:
       ```json
       {
         "title": "Learn Node.js",
         "description": "Understand the basics of Node.js",
         "status": "Pending"
       }
       ```
     - Click `Send` to create a task.
   - GET `/tasks`:
     - Select `GET` method and enter `http://localhost:3000/tasks`.
     - Click `Send` to retrieve all tasks.
   - GET `/tasks/:id`:
     - Replace `:id` with the task ID from the response of `/tasks`.
     - Click `Send` to retrieve a specific task.
   - PUT `/tasks/:id`:
     - Replace `:id` with the task ID from the response of `/tasks`.
     - Change the request method to `PUT`.
     - Enter the JSON body with updated values:
       ```json
       {
         "title": "Learn MongoDB",
         "description": "Understand the basics of MongoDB",
         "status": "In Progress"
       }
       ```
     - Click `Send` to update the task.
   - DELETE `/tasks/:id`:
     - Replace `:id` with the task ID.
     - Change the request method to `DELETE`.
     - Click `Send` to delete the task.

---

## Deploying the API

1. Push to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit for Task Management API"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```

2. Deploy on Render:
   - Go to [Render](https://render.com/).
   - Create a new **Web Service** and connect your GitHub repository.
   - Set the build command to:
     ```bash
     npm install
     ```
   - Set the start command to:
     ```bash
     npm start
     ```
   - Add the `MONGO_URI` environment variable in the Render dashboard.

3. Share the Live URL:
   - Render will provide a live URL for the API.
   - Use this URL in Postman to test the live API.

---

