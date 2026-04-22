# Module 13: JWT Authentication + Frontend + Playwright E2E

## Overview
This project extends the FastAPI backend from Module 12 by adding:

- JWT-based authentication (register/login)
- Frontend UI for login and registration
- Client-side validation (JavaScript)
- Playwright End-to-End (E2E) testing
- CI/CD pipeline with Docker and GitHub Actions

---

## Features

### Authentication
- `/register` creates a user with a hashed password
- `/login` validates credentials and returns a JWT
- Tokens are stored in localStorage

### Frontend Pages
- `register.html` for user registration with validation
- `login.html` for login and JWT storage
- `dashboard.html` as a protected landing page

### Validation
- Email format validation
- Password rules:
  - Minimum 8 characters
  - Must include uppercase, lowercase, and a number
- Confirm password match

---

## Testing

### Integration Tests
```bash
docker compose exec web pytest tests/integration -v
Playwright E2E Tests
docker compose exec web pytest tests/e2e/test_fastapi_calculator.py -v

Tests include:

Positive Cases

Register valid user
Login valid user
JWT stored in browser

Negative Cases

Short password triggers frontend error
Incorrect login returns 401 error
Docker Setup
Build and Run
docker compose up -d --build
Stop
docker compose down
Running the Application

Open in browser:

http://localhost:8000/register
http://localhost:8000/login
CI/CD Pipeline

GitHub Actions automatically:

Runs unit and integration tests
Runs Playwright E2E tests
Builds the Docker image
Pushes the image to Docker Hub
Docker Hub

https://hub.docker.com/r/ssingh1119/module13_is601

Screenshots Included
GitHub Actions workflow showing successful run
Playwright tests passing
Register page functioning
Login page functioning
Tech Stack
FastAPI
PostgreSQL
SQLAlchemy
Pydantic
JWT Authentication
Playwright
Docker
GitHub Actions
Reflection

This module helped me understand how frontend and backend systems integrate through APIs. Implementing JWT authentication strengthened my understanding of secure login systems, including password hashing and token handling.

Adding client-side validation improved user experience by catching errors before sending requests to the server. The most valuable part was implementing Playwright E2E tests, which simulate real user interactions in a browser. This ensured that the full system—from UI to database—works correctly.

Debugging Docker and Playwright setup issues taught me how important environment configuration is in real-world development. Integrating everything into a CI/CD pipeline reinforced how automation ensures reliability and scalability.