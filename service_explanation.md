# Service Explanation

This file defines a Kubernetes Service to expose the Streamlit application.

## Details:
- **Kind**: Service.
- **Type**: NodePort (Exposes the service on each Node's IP at a static port).
- **Selector**: Targets pods with label `app: streamlit-app`.
- **Ports**:
  - **Port**: 8080 (Service port).
  - **TargetPort**: 8080 (Container port).
  - **NodePort**: 30000 (External access port).
