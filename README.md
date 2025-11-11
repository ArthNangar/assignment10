# FastAPI Secure User Model — Module 10

### Overview  
This project is part of Module 10: Secure User Model, Pydantic Validation, Database Testing, and Docker Deployment.  
It builds upon earlier modules and focuses on creating a secure, production-ready FastAPI application using SQLAlchemy, Pydantic, and PostgreSQL— all fully tested and deployed through **GitHub Actions and Docker Hub.

---

## Features

**Secure User Model** – Implements a SQLAlchemy model with unique constraints for username & email, password hashing using bcrypt, and timestamp tracking.  
**Pydantic Schemas** – Validates user input through `UserCreate` and `UserRead` schemas ensuring strong typing and field validation.  
**SQLAlchemy ORM** – Handles database operations safely using sessions, commits, and relationships in a clean object-oriented way.  
**Password Hashing & Verification** – Hashes plain passwords before storing them and provides verification methods for authentication.  
**Full Testing Suite** – Unit + Integration tests covering password hashing, schema validation, and unique constraints against a real PostgreSQL database.  
**CI/CD Pipeline** – Automates test execution and image deployment through GitHub Actions and Docker Hub.  
**Docker Deployment** – Runs the app, Postgres, and pgAdmin inside containers for a complete development and testing environment.

---

## 🗂 Project Structure
```

assignment10/
├── .github/
│   └── workflows/
│       └── test.yml                  # GitHub Actions workflow for CI/CD
│
├── app/
│   ├── auth/
│   │   ├── __init__.py
│   │   └── dependencies.py         
│   │
│   ├── models/
│   │   ├── __init__.py
│   │   └── user.py                  
│   │
│   ├── operations/
│   │   └── __init__.py        
│   │
│   ├── schemas/
│   │   ├── __init__.py
│   │   ├── config.py
│   │   ├── database.py             
│   │   ├── database_init.py         
│   │
│   ├── templates/
│   │   └── index.html              
│   │
│   └── __init__.py                  
│
├── tests/
│   ├── e2e/ckage
│   │   ├── __init__.py
│   │   └── test_e2e.py               
│   │
│   ├── integration/
│   │   ├── __init__.py
│   │   ├── test_database.py          
│   │   ├── test_dependencies.py      
│   │   ├── test_fastapi_calculator.py
│   │   ├── test_schema_base.py       
│   │   ├── test_user_auth.py         
│   │   └── test_user.py              
│   │
│   ├── unit/
│   │   ├── __init__.py
│   │   └── test_calculator.py        
│   │
│   ├── __init__.py
│   └── conftest.py                   
│
├── .gitignore                        
├── docker-compose.yml                
├── Dockerfile                        
├── LICENSE                           
├── main.py                           
├── pytest.ini                        
├── README.md                         
└── requirements.txt                  

```

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

```bash

git clone https://github.com/ArthNangar/assignment10.git
cd assignment10

python -m venv venv
source venv/bin/activate
# On Windows:
# venv\Scripts\activate

pip install -r requirements.txt

docker compose up -d

Then open your browser at 👉 http://localhost:8000

pgAdmin is available at 👉 http://localhost:5050

🧪 Running Tests

pytest --cov=app tests/

```

## CI/CD Pipeline

The GitHub Actions workflow automatically runs on every push and pull request.

Test – Executes all unit & integration tests with PostgreSQL service container.

Security – Scans built Docker images using Trivy for vulnerabilities.

Deploy – Builds and pushes the Docker image to Docker Hub upon successful tests.

## Required GitHub Secrets
DOCKERHUB_USERNAME

DOCKERHUB_TOKEN

Docker Hub Link:  https://hub.docker.com/repository/docker/arthnangar7/module10

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments

FastAPI Documentation

Docker Docs

PostgreSQL Docs

pgAdmin Docs


## 👨‍💻 Author
Arth Nangar

Date: 11/10/2025

Module 10