
# FastAPI Calculator Application

This project includes a calculator API and web interface where users can perform arithmetic operations such as add, subtract, multiply, and divide. The application includes user authentication and persists data using PostgreSQL. 

## Key Features
- Full-stack FastAPI application with REST API and web interface
- User authentication with JWT (access and refresh tokens)
- PostgreSQL database with SQLAlchemy ORM 
- Jinja2-based frontend UI for managing calculations
- BREAD operations for calculations 
- Client-side and server-side validation for user inputs
- End-to-end testing with Playwright for authentication and workflows
- Integration and unit testing with Pytest
- CI/CD pipeline with GitHub Actions and Docker Hub
- Security scanning with Trivy 

## Web Page Interfaces
- Home: application landing page 
- Login: user login 
- Register: account creation 
- Dashboard: perform calculations 
    - View: view performed calculation & details
    - Edit: edit performed calculation & update results 
    - Delete: delete performed calculation


## BREAD Endpoints for Calculations
- Browse (GET /calculations): Retrieve & display all calculations 
- Read (GET /calculations/{id}): Retrieve details of specific calculation
- Edit (PUT /calculations/{id}): Update an existing calculation
- Add (POST /calculations): Create a new calculation 
- Delete (DELETE /calculations/{id}): Remove a calculation 
---

## Docker Image

Docker Hub Repository

https://hub.docker.com/r/msh0626/601_module14/tags

---

## Project Installation

Clone the repository
```
git clone git@github.com:matthowarth26/is601_module14.git
cd is601_module14
```

Initialize virtual environment
```
python3 -m venv venv
source venv/bin/activate
```

Install required packages
```
pip install -r requirements.txt
playwright install
```

Run the project locally with docker
```
docker compose up --build
```

Application URLs:
FastAPI:
```
http://localhost:8000
```

pgAdmin: 
```
http://localhost:5050
```

## Running Tests Locally
Start database container
```
docker compose up -d --build
```

Run all tests
```
pytest 
```

Run end-to-end tests
```
pytest tests/e2e -v
```

Run integration tests
```
pytest tests/integration -v
```

Run unit tests
```
pytest tests/unit -v
```

Run coverage report
```
pytest --cov=app
```

---

## CI/CD Information

GitHub Actions automatically runs tests and builds the Docker image.

GitHub Actions Workflow:
 - Checkout code using `actions/checkout`
 - Set up Python environment using `actions/setup-python`
 - Install dependencies from `requirements.txt`
 - Run unit tests
 - Run integration tests
 - Run end-to-end tests
 - Generate coverage report 
 - Build Docker image 
 - Run security scan with Trivy
 - Push Docker Image to Docker Hub

Configuration File:
```
.github/workflows/test.yml
```
