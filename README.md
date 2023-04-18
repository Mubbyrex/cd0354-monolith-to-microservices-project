# Udagram Image Filtering Application

Udagram is a simple cloud application. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

## Overview

This is my personal project aimed at converting a monolith application into a microservice architecture. The main goal of this project is to improve scalability, maintainability, and deployment flexibility of the application by leveraging microservices and cloud services provided by AWS, as well as modern DevOps tools like Circle CI, Docker, and Kubernetes.

## Technologies Used

- AWS RDS: Used to store metadata of the application.
- AWS S3: Used to store images.
- Nginx Reverse Proxy: Used as a means of communication between the frontend and the backend services.
- Docker: Used for containerization of the services.
- Kubernetes: Used for container orchestration and deployment.
- Circle CI: Used for continuous integration and continuous deployment (CI/CD).
  -Git: Used for version control and collaborative development.

## Project Structure

The project has been divided into the following components:

Backend Services: The original monolith application has been split into two independent backend services. These services are deployed as separate containers using Docker and orchestrated with Kubernetes. They communicate with each other through the Nginx Reverse Proxy.

Frontend Service: The frontend service remains unchanged and communicates with the backend services through the Nginx Reverse Proxy.

AWS RDS: The metadata of the application is stored in an AWS RDS database. The backend services communicate with the RDS database to retrieve and store metadata.

AWS S3: The images used in the application are stored in an AWS S3 bucket. The backend services communicate with the S3 bucket to upload and retrieve images.

Nginx Reverse Proxy: A separate service running Nginx is used as a reverse proxy to communicate between the frontend and backend services. It handles routing and load balancing between the backend services.

Circle CI: Circle CI is used for continuous integration and continuous deployment (CI/CD). It is configured to automatically build, test, and deploy the application to the Kubernetes cluster when changes are pushed to the repository.

Docker and Kubernetes: Docker is used for containerization of the services, and Kubernetes is used for container orchestration and deployment. Docker images are built and pushed to a container registry, and Kubernetes is used to deploy and manage the containers in a cluster.

### Setup and Deployment
To set up and deploy the application, follow these steps:

Set up an AWS RDS database for storing metadata of the application.
Set up an AWS S3 bucket for storing images used in the application.
Build Docker images for the backend and frontend services, and push them to a container registry.
Set up a Kubernetes cluster and deploy the Docker containers using Kubernetes manifests.
Set up the Nginx Reverse Proxy service using a Docker container and configure it to route traffic to the backend services.
Set up Circle CI to automatically build, test, and deploy the application to the Kubernetes cluster when changes are pushed to the repository.
For detailed instructions on how to set up and deploy the application, please refer to the documentation in the respective directories of each component.

### Conclusion
This project demonstrates the conversion of a monolith application into a microservice architecture using various AWS services, Nginx Reverse Proxy, Docker, and Kubernetes. It also showcases the implementation of CI/CD using Circle CI for automated building, testing, and deployment. I hope this project serves as a useful reference for others interested in similar topics. Please feel free to reach out to me with any questions or feedback.

The [JOURNAL.md](/Journal.md) file contains a walkthrough of the project being built
