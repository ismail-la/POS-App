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
