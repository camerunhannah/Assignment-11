Module 10: Secure User Model with CI/CD
This repository contains the solution for Module 10, focusing on building a secure user authentication system within a FastAPI application, integrating with a PostgreSQL database, and establishing a robust Continuous Integration/Continuous Delivery (CI/CD) pipeline using Docker and GitHub Actions.

Project Overview
The primary objective of this module was to extend foundational database knowledge to implement a secure user model. This involved defining a User model with SQLAlchemy for persistent storage, validating user data with Pydantic, and ensuring password security through hashing. A comprehensive CI/CD pipeline was configured to automate testing, security scanning, and deployment of the Dockerized application to Docker Hub, adhering to modern DevOps principles.

Key Features and Learning Outcomes
This project demonstrates:

Secure User Model: Implementation of a User model storing hashed passwords and enforcing unique constraints for username and email.

Data Validation: Use of Pydantic schemas (UserCreate, UserRead) for robust validation and serialization of user data.

Automated Testing: Development and execution of unit and integration tests, with integration tests leveraging a PostgreSQL container within GitHub Actions.

CI/CD Pipeline: A fully automated workflow to build, scan (using Trivy), and deploy the Docker image to Docker Hub upon successful test completion.

Containerization: Application of Docker for containerizing the FastAPI application.

Database Integration: Integration with a SQL database (PostgreSQL) for data creation and manipulation.

How to Run Tests Locally
To set up the project and run tests on your local machine, follow these steps:

Clone the repository:

git clone git@github.com:camerunhannah/Assignment-10.git
cd Assignment-10/module10_is601

Create and activate a Python virtual environment:

python -m venv venv
source venv/bin/activate

Install project dependencies:

pip install --upgrade pip
pip install -r requirements.txt

Install Playwright browser dependencies (for end to end tests):

sudo ../venv/bin/playwright install-deps

Start Docker Compose services (PostgreSQL, pgAdmin, and FastAPI app):
Ensure Docker Desktop is running. Navigate to the module10_is601 directory if you are not already there. If you encounter any conflicts, run docker compose down -v first.

docker compose up --build -d

Run tests:

pytest

CI/CD Pipeline and Docker Hub Deployment
This project utilizes GitHub Actions for its CI/CD pipeline. Upon every push to the main branch, the workflow automatically:

Checks out the code.

Sets up Python and caches pip dependencies.

Installs project dependencies.

Runs all unit, integration, and end to end tests against a dedicated PostgreSQL container.

Builds the Docker image for the application.

Scans the Docker image for vulnerabilities using Trivy.

