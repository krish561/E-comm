# E-Commerce Microservices Platform

A modern e-commerce platform built with microservices architecture, featuring a React frontend and Spring Boot backend services.

## Features

- 🛍️ Product catalog with categories and search
- 🛒 Shopping cart functionality
- 💳 Secure payment processing
- 📦 Order management
- 📊 Inventory tracking
- 🔍 Real-time stock updates
- 🔐 User authentication and authorization

## Technology Stack

### Frontend

- React 18.2.0
- Material-UI 5.15.11
- Vite 5.1.3
- React Router 6.22.1

### Backend

- Java 17
- Spring Boot 3.2.3
- Spring Cloud 2023.0.0
- Spring Data JPA
- PostgreSQL 15

### Infrastructure

- Docker & Docker Compose
- Apache Kafka 3.6.1
- Redis 3.1.0
- PostgreSQL 15

## Prerequisites

Before running the application, ensure you have the following installed:

1. **Java 17 (JDK)**

   - Download from: https://adoptium.net/
   - Required for running Spring Boot applications

2. **Node.js (v18 or higher)**

   - Download from: https://nodejs.org/
   - Required for running the React frontend

3. **Docker Desktop**

   - Download from: https://www.docker.com/products/docker-desktop
   - Required for running Kafka, Redis, and PostgreSQL

4. **Maven**
   - Download from: https://maven.apache.org/download.cgi
   - Required for building Java applications

## Quick Start

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd ecommerce-platform
   ```

2. Start the infrastructure services:

   ```bash
   docker-compose up -d
   ```

3. Build and start the backend services:

   ```bash
   mvn clean install
   ```

4. Start the frontend development server:
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

## Accessing the Application

- Frontend: http://localhost:5173 (or http://localhost:5174 if 5173 is in use)
- Order Service API: http://localhost:8081
- Inventory Service API: http://localhost:8082
- Payment Service API: http://localhost:8083

## API Documentation

Each service exposes its own Swagger UI documentation:

- Order Service: http://localhost:8081/swagger-ui.html
- Inventory Service: http://localhost:8082/swagger-ui.html
- Payment Service: http://localhost:8083/swagger-ui.html

## Project Structure

```
ecommerce-platform/
├── frontend/                 # React frontend application
│   ├── src/
│   │   ├── components/      # Reusable React components
│   │   ├── pages/          # Page components
│   │   └── App.jsx         # Main application component
│   └── package.json        # Frontend dependencies
├── order-service/          # Order management microservice
├── inventory-service/      # Inventory management microservice
├── payment-service/        # Payment processing microservice
├── docker-compose.yml      # Docker services configuration
└── pom.xml                # Maven parent POM
```

## Database Schema

The application uses three PostgreSQL databases:

1. **Order Database**

   - Stores order information
   - Tracks order status
   - Manages order items

2. **Inventory Database**

   - Manages product catalog
   - Tracks stock levels
   - Handles product categories

3. **Payment Database**
   - Processes transactions
   - Stores payment information
   - Manages payment status

## Troubleshooting

### Common Issues

1. **Port Conflicts**

   - Frontend: 5173/5174
   - Backend Services: 8081-8083
   - Kafka: 9092
   - Redis: 6379
   - PostgreSQL: 5432-5434

2. **Database Connection Issues**

   - Verify PostgreSQL containers are running:
     ```bash
     docker-compose ps
     ```
   - Check database credentials in application.yml files

3. **Kafka Connection Issues**
   - Ensure Zookeeper is running:
     ```bash
     docker-compose ps zookeeper
     ```
   - Check Kafka broker configuration

### Viewing Logs

```bash
# View all service logs
docker-compose logs -f

# View specific service logs
docker-compose logs -f order-service
docker-compose logs -f inventory-service
docker-compose logs -f payment-service
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
