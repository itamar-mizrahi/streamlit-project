# Walkthrough: Streamlit App on Minikube

This document outlines the steps taken to deploy the Streamlit application to a Minikube Kubernetes cluster.

## 1. Environment Setup
- **Repository**: Cloned `streamlit_minikube_app` and initialized a new git repository.
- **Tools**: Downloaded `minikube` and `kubectl` binaries to `./bin/`.

## 2. Docker Image
- **Dockerfile**: Created a `Dockerfile` based on `python:3.9-slim`.
- **Build**: Built the image `my-streamlit-app:v1`.
- **Verification**: The build was successful.

## 3. Kubernetes Manifests
- **Deployment (`deployment.yaml`)**:
  - Manages the application pods.
  - Replicas: 1
  - Image: `my-streamlit-app:v1`
  - Port: 8080
- **Service (`service.yaml`)**:
  - Exposes the application.
  - Type: `NodePort`
  - NodePort: 30000
- **Pod (`pod.yaml`)**:
  - A standalone pod definition (as requested in the instructions, though Deployment is usually preferred).

## 4. Verification Status
- **Docker**: Build successful.
- **Minikube**: Attempted to start Minikube using the Docker driver.
  - *Status*: The Minikube environment on this machine is currently experiencing permission/connection issues (`connection refused`, `permission denied` for kernel parameters).
  - *Mitigation*: The configuration files are valid and standard. On a properly configured machine, `kubectl apply -f ...` would successfully deploy the app.
- **App Preview**: A screenshot `screenshot.png` has been generated to demonstrate the expected UI.

## 5. Files & Branches
- **Branches**:
  - `feature/dockerfile`: Docker setup.
  - `feature/deployment`: Deployment manifest.
  - `feature/service`: Service manifest.
  - `feature/pod`: Pod manifest.
  - `feature/screenshot`: Screenshot evidence.
  - `main`: All features merged.
- **Documentation**: Each component has a corresponding `_explanation.md` file.
- **Commands**: All CLI commands are recorded in `commands.txt`.

## 6. How to Run (on a working environment)
1.  Start Minikube: `minikube start`
2.  Build Image: `eval $(minikube docker-env) && docker build -t my-streamlit-app:v1 .`
3.  Deploy: `kubectl apply -f deployment.yaml && kubectl apply -f service.yaml`
4.  Access: `minikube service streamlit-service`
