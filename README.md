# E-Commerce Web Application

## Overview
This project is a fully-featured e-commerce web application built using the Go programming language. It provides a robust backend for handling core e-commerce functionality such as product management, user authentication, and order processing. The application is designed with scalability and security in mind, utilizing token-based authentication (JWT) and containerization through Docker for smooth deployment and management.

## Features
- **User Authentication**: Secure user signup, login, and token-based authentication using JWT.
- **Product Management**: Add, update, view, and delete products.
- **Order Processing**: Handle customer orders and manage order statuses.
- **Middleware**: Secure access with middleware for authentication.
- **Docker Integration**: Simplified deployment using Docker and Docker Compose.
- **RESTful API**: Structured and scalable API design for managing requests and resources.

## Project Structure
- **controllers/**: Contains the business logic for handling HTTP requests and sending responses.
- **database/**: Responsible for database connection setup and migrations.
- **middleware/**: Authentication and other middleware for securing API endpoints.
- **models/**: Defines the data models for users, products, and orders, representing database entities.
- **routes/**: API routing and endpoint management.
- **Dockerfile & docker-compose.yml**: Configuration for containerizing the application and managing services.

## Technologies Used
- **Go**: Backend development
- **PostgreSQL**: Database management
- **JWT**: Token-based authentication
- **Docker**: Containerization for deployment
- **Gorilla Mux**: HTTP router for Go

## Setup Instructions

### Prerequisites
- Docker installed on your machine.
- Go 1.18+ for local development.

### Steps to Run Locally

#### Clone the repository:
```bash
git clone https://github.com/Srishti0610/ecommerce-yt.git
cd ecommerce-yt
```
#### Start the application using Docker Compose:
```bash
docker-compose up
```
This will spin up the necessary containers for the application and database.

Access the application via localhost:8000.

# API Endpoints

- **POST /signup**: Create a new user.
- **POST /login**: Authenticate and generate JWT.
- **GET /products**: Retrieve a list of products.
- **POST /products**: Add a new product (admin only).
- **PUT /products/{id}**: Update product details (admin only).
- **DELETE /products/{id}**: Delete a product (admin only).
- **POST /order**: Place a new order.
- **GET /orders**: Retrieve orders (user-specific).

# Database Schema

## User
- **Fields**: 
  - `username`: String
  - `email`: String
  - `password`: String

## Product
- **Fields**: 
  - `name`: String
  - `description`: String
  - `price`: Decimal
  - `stock`: Integer

## Order
- **Fields**: 
  - `userId`: Foreign key linking to User
  - `productId`: Foreign key linking to Product
  - `status`: String (e.g., pending, completed, canceled)
  - `orderDate`: DateTime
