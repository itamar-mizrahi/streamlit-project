# Deployment Explanation

This file defines a Kubernetes Deployment for the Streamlit application.

## Details:
- **Kind**: Deployment (manages Pods and replicas).
- **Replicas**: 1 instance.
- **Selector**: Matches pods with label `app: streamlit-app`.
- **Container**:
  - **Image**: `user123/streamlit-app:v1` (The Docker image we built).
  - **Port**: 8080.
  - **ImagePullPolicy**: `IfNotPresent` (Use local image if available).
