# User Management REST API

## Overview
A production-style RESTful API for user CRUD operations built with Java Spring Boot,
containerised with Docker, and deployed on AWS EC2.

## Architecture
      ┌──────────────────────────────┐
      │   Client                     │
      │   (Postman / Frontend)       │
      └──────────────┬───────────────┘
                     │  HTTP Request
                     ▼
      ┌──────────────────────────────┐
      │   REST Controller Layer      │
      │   /api/users  (5 endpoints)  │
      └──────────────┬───────────────┘
                     │
                     ▼
      ┌──────────────────────────────┐
      │   Service Layer              │
      │   Business Logic             │
      └──────────────┬───────────────┘
                     │
                     ▼
      ┌──────────────────────────────┐
      │   Repository Layer           │
      │   Spring Data JPA            │
      └──────────────┬───────────────┘
                     │
                     ▼
      ┌──────────────────────────────┐
      │   MySQL Database             │
      └──────────────────────────────┘
                     │
                     ▼
      ┌──────────────────────────────┐
      │   Docker Container           │
      └──────────────┬───────────────┘
                     │
                     ▼
      ┌──────────────────────────────┐
      │   AWS EC2                    │
      └──────────────────────────────┘

## Tech Stack
- **Language:** Java 17
- **Framework:** Spring Boot, Spring Data JPA
- **Database:** MySQL
- **Containerisation:** Docker
- **Cloud:** AWS EC2
- **Testing:** Postman (100% endpoint coverage)

## API Endpoints
| Method | Endpoint | Description |
|---|---|---|
| GET | /api/users | Get all users |
| GET | /api/users/{id} | Get user by ID |
| POST | /api/users | Create new user |
| PUT | /api/users/{id} | Update user |
| DELETE | /api/users/{id} | Delete user |

## Design Patterns Used
- Layered architecture: Controller → Service → Repository
- DTO pattern for request/response separation
- Exception handling with custom error responses

## Note
AWS EC2 instance decommissioned after free tier expiry.
Code reflects the full implementation — Docker and deployment configs included.
