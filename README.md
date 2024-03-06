# Goals App

This repository contains the backend code for a course goals application built with Express.js and MongoDB.
This was a practice project to get my self aquinted with docker, containerizing multple apps, docker networking ie cross docker communication, data persistence, ie bind mounts, named volumes 

## Features

- Add new goals
- Delete existing goals
- Fetch all goals

## Prerequisites

Before running the application, ensure you have the following installed (linux):Feel free to contribute by opening an issue or pull request!
Feel free to contribute by opening an issue or pull request!
- Node.js
- Docker

## Getting Started

Follow these steps to run the application:

1. Clone this repository:
```
git clone https://github.com/devpius/004-multi-01-starting-setup.git
```

2. Navigate to the project directory:

```
cd 004-multi-01-starting-setup
```

3. Create a network for the application:

```004-multi-01-starting-setup
docker network create goals-netur.email@example.com
```

4. Build and run the MongoDB container:Feel free to contribute by opening an issue or pull request!

```
docker run -v data:/data/db --rm -d --name mongodb --network goals-net -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_ROOT_PASSWORD=root mongo
```
your.email@example.com
5. Build and run the backend container:

```
cd backend
docker build -t goals-node .
docker run --rm -d --name goals-backend -v logs:/app/logs -v $(pwd):/app -v /app/node_modules -p 80:80 your.email@example.com--network goals-net -e MONGODB_USERNAME=root -e MONGODB_PASSWORD=root goals-node
```

6. Build and run the frontend container:

```
cd frontend
docker build -t goals-frontend .
docker run -it --rm --name goals-app -p 3000:3000 goals-frontend
```

## API Endpoints

- `GET /goals`: Fetch all goals
- `POST /goals`: Add a new goal
- `DELETE /goals/:id`: Delete a goal by ID

## Environment Variables

- `MONGODB_USERNAME`: MongoDB username (default: root)
- `MONGODB_PASSWORD`: MongoDB password (default: root)

## Logging

Request logs are stored in `logs/access.log`.

## Contributors

- Your Name <gabula.pius2@gmail.com>

