Module 11: Secure User Model with CI/CD
This repository contains the solution for Module 11, which builds upon foundational database knowledge to implement a secure user authentication system within a FastAPI application. It integrates with a PostgreSQL database and establishes a robust Continuous Integration/Continuous Delivery (CI/CD) pipeline using Docker and GitHub Actions.

Project Overview
The primary objective of this module was to implement and finalize a secure user model, ensuring data validation and password security. A comprehensive CI/CD pipeline was configured to automate testing, security scanning, and deployment of the Dockerized application to Docker Hub, adhering to modern DevOps principles. This module serves as a complete demonstration of building, testing, and deploying a secure web application.

Key Features and Learning Outcomes
This project demonstrates:

Secure User Model: Implementation of a User model using SQLAlchemy, storing hashed passwords, and enforcing unique constraints for username and email.

Data Validation: Use of Pydantic schemas (UserCreate, UserRead) for robust validation of incoming user data and secure serialization of outgoing responses.

Automated Testing: Development and execution of comprehensive unit, integration, and end-to-end (E2E) tests. Integration tests leverage a PostgreSQL container within GitHub Actions for real database interactions.

CI/CD Pipeline: A fully automated workflow to build the Docker image, scan it for vulnerabilities (using Trivy), and deploy it to Docker Hub upon successful test and security scan completion.

Containerization: Application of Docker and Docker Compose for containerizing the FastAPI application and its dependencies (PostgreSQL, pgAdmin).

Database Integration: Integration of the Python application with a SQL database (PostgreSQL) to create and manipulate data programmatically.

DevOps Principles: Practical application of Continuous Integration, Continuous Delivery, and security automation.

How to Run Tests Locally
To set up the project and run tests on your local machine, follow these steps:

Clone the repository:

git clone https://github.com/camerunhannah/Assignment-11.git
cd Assignment-11/module11_is601


Create and activate a Python virtual environment:

python -m venv venv
source venv/bin/activate

Install project dependencies:

pip install --upgrade pip
pip install -r requirements.txt

Install Playwright browser dependencies (for end-to-end tests):

sudo ../venv/bin/playwright install-deps

Start Docker Compose services (PostgreSQL, pgAdmin, and FastAPI app):
Ensure Docker Desktop is running. Navigate to the module11_is601 directory if you are not already there. If you encounter any conflicts, run docker compose down -v first to clear all old containers and volumes.

docker compose up --build -d

Run tests:

pytest

CI/CD Pipeline and Docker Hub Deployment
This project utilizes GitHub Actions for its robust CI/CD pipeline. Upon every push to the main branch, the workflow automatically:

Checks out the code.

Sets up Python and caches pip dependencies.

Installs project dependencies.

Runs all unit, integration, and end-to-end tests against a dedicated PostgreSQL container.

Builds the Docker image for the application.

Scans the Docker image for vulnerabilities using Trivy.

If all tests and security scans pass, the Docker image is pushed to Docker Hub.


