# Project Description

This project is a simple Todo application with two backend servers: one written in Go and the other in Python using FastAPI. 
Both servers interact with a PostgreSQL database to manage Todo items.


## How to Run

### Prerequisites

- Docker
- Docker Compose

### Steps

Servers are packaged as Docker images in Docker Hub. 

1. **Build and run the services using Docker Compose:**

```
docker compose up -d
```

2. **Access the servers:**
    - Go server: `http://localhost:8080`
    - Python server: `http://localhost:9090`

### API Endpoints

Both servers expose the following endpoints:

- `GET /todos`: Retrieve all todos.
- `GET /todos/{id}`: Retrieve a todo by ID.
- `POST /todos`: Create a new todo.
- `PATCH /todos/{id}`: Toggle the completion status of a todo.

### Environment Variables

The following environment variables are used to configure the database connection:

- `DB_NAME`: Name of the database.
- `DB_USER`: Database user.
- `DB_PASSWORD`: Database password.
- `DB_HOST`: Database host.
- `DB_PORT`: Database port.

These variables are set in the `docker-compose.yml` file.

### Database Initialization

The database is initialized with a table for todos using the `init.sql` script.

Table will be empty. If you put some data into the table and don't remove `postgres_data` volume from your Docker env., data will persist even if you restart the DB

### Stats

To monitor container resource utilisation use the following command 

```sh
docker stats
```
Resource limits for each container are located in `docker-compose.yml` file

### Shutting Down

```sh
docker compose down
```