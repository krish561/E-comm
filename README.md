# E-comm

# E-Commerce Microservices Platform

This project implements a microservices-based e-commerce platform using Spring Boot, Kafka, and Redis.

## Required Software

Before running the application, please install the following software:

1. **Java 17** (JDK)

   - Download from: https://adoptium.net/
   - Required for running Spring Boot applications

2. **Maven**

   - Download from: https://maven.apache.org/download.cgi
   - Required for building Java applications

3. **Node.js** (v16 or higher)

   - Download from: https://nodejs.org/
   - Required for running the React frontend

4. **Docker Desktop**

   - Download from: https://www.docker.com/products/docker-desktop
   - Required for running Kafka, Redis, and PostgreSQL

5. **Docker Compose**
   - Usually comes with Docker Desktop
   - If not, download from: https://docs.docker.com/compose/install/

## Quick Start

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd ecommerce-platform
   ```

2. Make the startup script executable:

   ```bash
   chmod +x start.sh
   ```

3. Run the startup script:
   ```bash
   ./start.sh
   ```

The script will:

- Check if all required software is installed
- Start all infrastructure services (Kafka, Redis, PostgreSQL)
- Build and start all backend services
- Start the frontend application

## Accessing the Application

- Frontend: http://localhost:3000
- Order Service API: http://localhost:8081
- Inventory Service API: http://localhost:8082
- Payment Service API: http://localhost:8083

## API Documentation

Each service exposes its own Swagger UI documentation:

- Order Service: http://localhost:8081/swagger-ui.html
- Inventory Service: http://localhost:8082/swagger-ui.html
- Payment Service: http://localhost:8083/swagger-ui.html

## Architecture

The platform consists of the following microservices:

1. **Order Service**: Handles order processing and management
2. **Inventory Service**: Manages product inventory and stock
3. **Payment Service**: Processes payments and transactions
4. **Frontend**: React-based web application

## Technology Stack

- Java 17
- Spring Boot 3.x
- Apache Kafka for event-driven communication
- Redis for caching
- Docker for containerization
- React for frontend
- Material-UI for frontend components

## Troubleshooting

### Common Issues

1. Port conflicts:

   - Ensure no other services are running on ports 8081-8083
   - Check if Kafka (9092) and Redis (6379) ports are available

2. Database connection issues:

   - Verify PostgreSQL containers are running
   - Check database credentials in application.yml files

3. Kafka connection issues:
   - Ensure Zookeeper is running
   - Check Kafka broker configuration

### Logs

View service logs:

```bash
# Order Service
docker-compose logs order-service

# Inventory Service
docker-compose logs inventory-service

# Payment Service
docker-compose logs payment-service
```
