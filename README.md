CI/CD Pipeline Project
Overview

This project demonstrates a complete Continuous Integration and Continuous Deployment (CI/CD) pipeline. The pipeline automatically tests, builds, and deploys the application whenever changes are made to the repository. It ensures consistency, improves code quality, and reduces deployment time.

Features

Automated builds on every push or pull request

Automated testing and linting

Docker image build and publishing

Deployment to the target environment

Artifact storage and versioning

Notifications on pipeline success or failure

Tech Stack

Git + GitHub

GitHub Actions (CI/CD)

Docker

Node.js Application

AWS EC2 for deployment

Project Structure
.
├── .github/workflows/ci.yml
├── .github/workflows/cd.yml
├── src/
├── tests/
├── Dockerfile
├── docker-compose.yml
└── README.md

CI Pipeline (ci.yml)

The CI pipeline runs on every push and pull request.
It performs the following:

Checkout code

Install dependencies

Run tests

Lint code

Build Docker image

Upload artifacts

CD Pipeline (cd.yml)

The CD pipeline runs on merges to the main branch.
It performs the following:

Pull artifacts from CI

Authenticate with AWS

Deploy Docker container to EC2

Run health checks

Notify on completion

Local Setup

Clone the repository:

git clone https://github.com/your/repo.git
cd repo


Install dependencies:

npm install


Run tests:

npm test


Run locally:

npm start

Docker Usage

Build:

docker build -t cicd-app .


Run:

docker run -p 3000:3000 cicd-app

Environment Variables

Add the following secrets to GitHub Actions:

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
EC2_HOST
EC2_USERNAME
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN

Deployment

Deployment is fully automated through the CD pipeline.
Merging into main triggers:

Build

Push Docker image

SSH into EC2

Pull and run updated container

No manual steps are required.

Contributing

Create a new branch

Make your changes

Create a pull request

Ensure your PR passes CI

License

MIT License.