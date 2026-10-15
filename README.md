# CI/CD Pipeline and Cloud Deployment Automation

## Project Overview

This project demonstrates an automated CI/CD pipeline using Jenkins, GitHub, Docker, and AWS EC2. Whenever code is pushed to the GitHub repository, Jenkins automatically triggers the pipeline, builds a Docker image, deploys the application, and verifies the deployment.

## Technologies Used

- **Git & GitHub** — Source code management and version control
- **Jenkins** — CI/CD pipeline automation
- **Docker** — Application containerization
- **Linux (Ubuntu)** — Server environment
- **AWS EC2** — Cloud deployment platform
- **Nginx** — Web server for hosting the application

## Architecture

Developer → GitHub → Webhook → Jenkins → Docker Build → Container Deployment → AWS EC2

## Project Files

| File | Description |
|---|---|
| `index.html` | Website source code |
| `Dockerfile` | Instructions to build the Docker image |
| `Jenkinsfile` | Defines the automated CI/CD pipeline |
| `README.md` | Project documentation |

## CI/CD Pipeline Stages

1. **Checkout:** Jenkins fetches source code from GitHub.
2. **Build:** Docker builds an image named `cicd-website`.
3. **Deploy:** Jenkins replaces the existing container and starts a new one named `cicd-container`.
4. **Verify:** The pipeline checks the running container and tests the HTTP response.

## Deployment

The application runs inside a Docker container on AWS EC2. The container maps port `8081` on the EC2 host to port `80` inside the container.

## How to Access

Open the following URL in your browser, replacing the placeholder with your EC2 public IP:

`http://<EC2-PUBLIC-IP>:8081`

## Key Learning Outcomes

- Version control using Git and GitHub
- Creating a Jenkins pipeline using a Jenkinsfile
- Building and running Docker containers
- Configuring GitHub webhooks
- Deploying a web application on AWS EC2
- Verifying automated deployments

## Project Status

Successfully implemented and tested. A GitHub code push triggers the Jenkins pipeline, which builds and deploys the application automatically.
