# Create a markdown file for the user's README content

readme_content = """
# Node.js Kubernetes Application

![Node.js](https://img.shields.io/badge/Node.js-v14-green) ![Docker](https://img.shields.io/badge/Docker-Enabled-blue) ![Kubernetes](https://img.shields.io/badge/Kubernetes-Deployed-orange)

A simple Node.js application that runs inside a Docker container, deployed on a Kubernetes cluster with a private Docker registry, ImagePullSecrets, and NGINX Ingress Controller.

## Table of Contents

- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Docker Setup](#docker-setup)
- [Kubernetes Deployment](#kubernetes-deployment)
  - [ImagePullSecret](#imagepullsecret)
  - [ClusterIP Service](#clusterip-service)
  - [NGINX Ingress Controller](#nginx-ingress-controller)
- [Accessing the Application](#accessing-the-application)
- [Scaling and Updating](#scaling-and-updating)
- [Cleanup](#cleanup)

## Project Overview

This project demonstrates how to deploy a Node.js application using Docker and Kubernetes. It includes setting up a Kubernetes **ImagePullSecret** for private Docker registry access and exposing the service using **NGINX Ingress**.

## Prerequisites

Before starting, make sure you have the following installed:

- [Docker](https://www.docker.com/)
- [Kubernetes (kubectl)](https://kubernetes.io/docs/tasks/tools/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/) (optional for local development)
- A Docker registry (e.g., [DockerHub](https://hub.docker.com/))

## Docker Setup

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <project-directory>
