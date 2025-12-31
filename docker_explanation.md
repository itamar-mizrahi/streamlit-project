# Dockerfile Explanation

This Dockerfile builds a container image for the Streamlit application.

## Steps:
1.  **Base Image**: Uses `python:3.9-slim` for a lightweight Python environment.
2.  **Working Directory**: Sets `/app` as the working directory.
3.  **Dependencies**: Copies `requirements.txt` and installs Python packages.
4.  **Application Code**: Copies the rest of the application code.
5.  **Expose Port**: Exposes port 8080.
6.  **Command**: Runs the Streamlit app on port 8080 and binds to 0.0.0.0 to make it accessible outside the container.
