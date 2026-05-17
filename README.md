# Digital Equb Management System

A web-based Digital Equb Management Platform built using Spring Boot that allows users to create, join, and manage Equb groups online.

---

# Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [System Roles](#system-roles)
- [Technologies Used](#technologies-used)
- [System Architecture](#system-architecture)
- [Project Structure](#project-structure)
- [Database Design](#database-design)
- [API Endpoints](#api-endpoints)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Project](#running-the-project)
- [Testing](#testing)
- [Future Improvements](#future-improvements)
- [Security Considerations](#security-considerations)
- [Contributors](#contributors)
- [License](#license)

---

# Introduction

The Digital Equb Management System is a platform that modernizes the traditional Ethiopian Equb system by allowing users to manage Equb groups digitally.

The system supports:
- User registration and authentication
- Equb group creation and management
- Join request approval system
- National ID upload and verification
- Group chat system
- Payment tracking
- Random Equb receiver selection
- Multiple Equb groups with different configurations

This project is developed as an Advanced Java Programming project using Spring Boot and MySQL.

---

# Features

## Authentication
- User registration
- User login
- JWT-based authentication
- Role-based authorization

---

## Equb Group Management
- Create Equb groups
- Search groups by:
  - region
  - contribution amount
  - payment frequency
- Join multiple Equb groups
- Group membership management

---

## Join Request System

Users can:
- Send join requests
- Upload national ID documents
- Submit bank account information

Admins can:
- Accept requests
- Reject requests
- Review uploaded documents

---

## Payment Management

- Members send money to the group admin
- Payment tracking system
- Paid/unpaid member monitoring
- Payment history management

---

## Random Receiver Selection

- Randomly select Equb receiver
- Prevent duplicate winners
- Store winner history

---

## Group Chat

- Real-time communication
- Private group chat rooms
- WebSocket-based messaging

---

# System Roles

## Member

Members can:
- Join Equb groups
- Send join requests
- Upload documents
- Participate in chats
- View group member information

---

## Admin

Admins can:
- Create Equb groups
- Manage members
- Approve/reject requests
- Confirm payments
- Manage group activities

---

# Technologies Used

## Backend
- Java
- Spring Boot
- Spring Security
- Spring Data JPA
- WebSocket
- JWT Authentication

---

## Database
- MySQL

---

## Build Tool
- Maven

---

## Testing Tools
- Postman

---

## Version Control
- Git
- GitHub

---

# System Architecture

```text
Client (Frontend)
       ↓
REST API + WebSocket
       ↓
Spring Boot Backend
       ↓
MySQL Database
```

---

# Project Structure

```text
src
 └── main
     ├── java
     │    └── com.equb
     │         ├── controller
     │         ├── service
     │         ├── repository
     │         ├── model
     │         ├── dto
     │         ├── security
     │         ├── websocket
     │         └── config
     │
     └── resources
          ├── application.properties
          └── static
```

---

# Database Design

## Tables

| Table Name | Description |
|------------|-------------|
| users | Stores user information |
| equb_groups | Stores Equb group details |
| memberships | Stores group memberships |
| join_requests | Stores pending requests |
| payments | Stores payment records |
| rounds | Stores Equb winners |
| chat_messages | Stores chat history |
| uploaded_documents | Stores uploaded IDs |

---

# API Endpoints

## Authentication

```http
POST /api/auth/register
POST /api/auth/login
```

---

## Group Management

```http
POST /api/groups/create
GET /api/groups
GET /api/groups/{id}
```

---

## Join Requests

```http
POST /api/groups/{id}/join
PUT /api/requests/{id}/approve
PUT /api/requests/{id}/reject
```

---

## Payments

```http
POST /api/payments/confirm
GET /api/payments/group/{id}
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/your-username/digital-equb-system.git
```

---

## Navigate to Project Folder

```bash
cd digital-equb-system
```

---

# Configuration

## Configure MySQL Database

Create a MySQL database:

```sql
CREATE DATABASE digital_equb;
```

---

## Update application.properties

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/digital_equb
spring.datasource.username=root
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

# Running the Project

## Run Using Maven

```bash
mvn spring-boot:run
```

---

## Default Server

```text
http://localhost:8080
```

---

# Testing

Use Postman to test the APIs.

## Example Tests
- Register user
- Login user
- Create Equb group
- Send join request
- Approve member
- Confirm payment

---

# Future Improvements

- telebirr integration
- Mobile application
- Automatic payment verification
- Email notifications
- SMS verification
- AI fraud detection
- Admin reputation system

---

# Security Considerations

- Password encryption using BCrypt
- JWT authentication
- File upload validation
- Role-based authorization
- Protected API endpoints

---

# Contributors

- Migbaru Belay Argachew

---

# License

This project is developed for educational purposes.
