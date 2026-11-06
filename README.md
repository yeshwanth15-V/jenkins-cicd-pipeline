# Jenkins CI/CD Pipeline

## Project Overview
This project demonstrates a simple Continuous Integration and Continuous Deployment (CI/CD) pipeline using Jenkins, GitHub, Docker, and Node.js.

The pipeline automatically checks out source code, builds a Docker image, runs application tests, and deploys the application in a Docker container.

## Technologies Used
- Node.js
- Express.js
- Jenkins
- Docker
- Git and GitHub

## CI/CD Pipeline Stages

1. **Checkout:** Retrieves source code from GitHub.
2. **Build:** Builds the Docker image.
3. **Test:** Runs application tests inside the Docker container.
4. **Deploy:** Deploys the application using Docker.

## Automatic Trigger
Jenkins uses SCM Polling to periodically check the GitHub repository for changes and trigger the pipeline automatically.

## Application Access
After successful deployment, access the application at:

`http://localhost:3001`

## Project Structure

```text
jenkins-cicd-pipeline/
├── Jenkinsfile
├── Dockerfile
├── app.js
├── package.json
├── package-lock.json
├── public/
└── test/
```

## How to Run

Clone the repository:

```bash
git clone https://github.com/yeshwanth15-V/jenkins-cicd-pipeline.git
cd jenkins-cicd-pipeline
```

Build the Docker image:

```bash
docker build -t jenkins-cicd-app:latest .
```

Run the application:

```bash
docker run -d --name jenkins-cicd-app -p 3001:3000 jenkins-cicd-app:latest
```

## Result
Successfully implemented and tested an automated Jenkins CI/CD pipeline with GitHub integration and Docker-based deployment.
