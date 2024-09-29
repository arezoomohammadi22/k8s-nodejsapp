###Node.js Docker Application

This project demonstrates a simple Node.js application that runs inside a Docker container. The project includes the setup for deploying the application in a Kubernetes cluster with an ImagePullSecret for private Docker registry access and an NGINX Ingress Controller for external access.

###Prerequisites

Before you begin, ensure you have the following installed:

Docker
Kubernetes (kubectl)
Minikube (optional for local development)
A Docker registry (e.g., DockerHub, or private registry)
Project Structure

server.js: The main Node.js application file.
package.json: Metadata and dependencies for the Node.js app.
Dockerfile: The configuration for building the Docker image.
1. Building the Docker Image

To build the Docker image, follow these steps:

Clone the repository:
```bash
git clone <repository-url>
cd <project-directory>
```
Build the Docker image:
```bash
docker build -t <your-docker-username>/myapp:v1 -f app/Dockerfile
```
Push the Docker image to your registry:
```bash
docker login
docker push <your-docker-username>/myapp:v1
```
Replace <your-docker-username> with your actual DockerHub username or private registry details.

2. Deploying to Kubernetes

2.1 Create ImagePullSecret
If you are using a private Docker registry (like DockerHub), you need to create a secret in Kubernetes that allows the cluster to pull images from your private registry.

Create an ImagePullSecret:
```bash
kubectl create secret docker-registry myregistrykey \
  --docker-server=https://index.docker.io/v1/ \
  --docker-username=<your-docker-username> \
  --docker-password=<your-docker-password> \
  --docker-email=<your-email>
```
Replace the placeholders:

<your-docker-username>: Your Docker registry username.
<your-docker-password>: Your Docker registry password.
<your-email>: Your email address.

