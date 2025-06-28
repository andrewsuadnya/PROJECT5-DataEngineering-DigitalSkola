# Flask CRUD API with PostgreSQL and Docker

## 📄 Project Overview

This project aims to build a simple CRUD API using **Flask** as the backend framework, **PostgreSQL** as the database, and **Docker** for containerization. The API provides basic user management functionality including:

* Create User
* Read User(s)
* Update User
* Delete User

The project also includes endpoints to check API health and database connectivity.

---

## 🚀 Tech Stack

* **Flask** for web API development
* **PostgreSQL** as the relational database
* **Docker** to containerize the application
* **Docker Compose** to orchestrate multi-container setup
* **DBeaver** for testing database connectivity
* **Postman** for testing API endpoints

---

## 🛠️ How to Run

### 1. Start Docker Desktop

Ensure Docker Desktop is running on your machine.

### 2. Create docker-compose.yml

This file defines two services:

* `db`: PostgreSQL container
* `flask-app`: Flask application container

### 3. Build Docker Image

```bash
docker build -t project-5-sib-digitalskola ./app
```

### 4. Create Docker Volume

```bash
docker volume create pg-data
```

### 5. Run Docker Compose

```bash
docker-compose up -d
```

### 6. Check Containers

```bash
docker ps
```

Ensure both `flask-app` and `db` containers are running.

### 7. Test PostgreSQL Connection

* Use DBeaver
* Host, port, username, and password are configured in docker-compose

### 8. Database Setup

Using DBeaver, create a `users` table with columns:

* `user_id` (INT, Primary Key)
* `name` (TEXT)
* `city` (TEXT)
* `telp` (TEXT)

### 9. Access Flask API

Open browser or Postman:

* `http://localhost:5000/health`
* `http://localhost:5000/db_check`

---

## 🔧 Available Endpoints

| Method | Endpoint    | Description          |
| ------ | ----------- | -------------------- |
| GET    | /health     | Check API health     |
| GET    | /db\_check  | Check DB connection  |
| GET    | /user       | Get all users        |
| GET    | /user/\<id> | Get user by ID       |
| POST   | /user       | Add new user         |
| PUT    | /user/\<id> | Update existing user |
| DELETE | /user/\<id> | Delete user by ID    |

---

## 📁 Project Structure

```
project-folder/
├── app/
│   ├── main.py             # Flask API routes and logic
│   ├── Dockerfile          # Flask container setup
├── docker-compose.yml      # Define multi-container setup
├── requirements.txt        # Python dependencies
```
