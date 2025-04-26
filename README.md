# Simplified POS System

## Description

A modern, containerized POS (Point of Sale) system designed using microservices architecture. This project demonstrates how to create and deploy two independent microservices: `order-service` and `inventory-service`. The `order-service` creates orders, and the `inventory-service` listens for new orders via RabbitMQ to update product stock levels in MongoDB.

The application is built using **Node.js**, **Express.js**, **MongoDB**, **RabbitMQ**, and **Docker**, and it provides a simple yet powerful way to handle orders and inventory in a decoupled, scalable system.

## Key Features

- **Order Service**: Handles creation of new orders and sends messages to RabbitMQ.
- **Inventory Service**: Listens to RabbitMQ queues, processes order data, and updates product stock in the database.
- **MongoDB**: Used for storing orders and inventory data.
- **RabbitMQ**: Message broker for decoupling services and managing communication between them.
- **Docker & Docker Compose**: Containerized environment to run the services easily.

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Message Queue**: RabbitMQ (amqplib)
- **Containerization**: Docker, Docker Compose

## Project Structure

- **order-service**: Handles order creation and sends messages to the RabbitMQ queue.
- **inventory-service**: Consumes messages from RabbitMQ and updates the stock in the inventory database.
- **docker-compose.yml**: Defines the services (MongoDB, RabbitMQ, and the two microservices).
- **Dockerfile**: Used to containerize the services.

## How to Run Locally

1. **Clone the repository**:

   ```bash
   git clone https://github.com/yourusername/simple-pos-project.git
   cd simple-pos-project

   ```

2. **Build and start the services using Docker Compose**:
   docker-compose up --build

3. **Build and start the services using Docker Compose**:
   -Order Service: http://localhost:3000

-Inventory Service: http://localhost:3001

-RabbitMQ Dashboard: http://localhost:15672 (Login: guest / Password: guest)

4. **Build and start the services using Docker Compose**:
   -Create an order (POST request):
   curl -X POST http://localhost:3000/orders -H "Content-Type: application/json" -d '{"productId":"123", "quantity":2}'

-Check orders (GET request):
curl http://localhost:3000/orders

-Check inventory stock (GET request):
curl http://localhost:3001/inventory/123

License
This project is licensed under the MIT License - see the LICENSE file for details.
