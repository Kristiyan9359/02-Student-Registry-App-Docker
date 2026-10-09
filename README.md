# Student Registry App – CI/CD with Jenkins and Docker

## Overview
A Node.js web application for managing student records, configured with an automated CI/CD pipeline using Jenkins and Docker.

## Technologies
- Node.js and Express.js
- Mocha for automated testing
- Docker and Docker Hub
- Jenkins for CI/CD
- GitHub Webhooks for automatic pipeline triggers

## CI/CD Pipeline
1. **Install Dependencies** – Install Node.js packages.
2. **Run Tests** – Execute automated tests.
3. **Build Docker Image** – Build the application image.
4. **Push Docker Image** – Push the image to Docker Hub.
5. **Deploy** – Automatically trigger the CD job to deploy the latest image in a Docker container.

## Run Locally

```bash
npm install
npm start
```

Open http://localhost:3030 in your browser.

## Docker

```bash
docker pull kristiyan9359/student-registry:latest
docker run -d --name student-registry -p 3030:3030 kristiyan9359/student-registry:latest
```

## Purpose
This project demonstrates practical CI/CD automation with Jenkins, Docker image publishing, automated testing, and container deployment.