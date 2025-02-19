These configurations define two Kubernetes Deployments using the blue-green deployment strategy, which helps manage application updates with minimal downtime.

Description:
myprofile-blue Deployment:

Deploys version 2.0 of the masterb3/website container.
Runs 4 replicas of the application.
Labeled as release: v1, allowing traffic to be routed based on labels.
Limits container resources to 128Mi memory and 500m CPU.
myprofile-green Deployment:

Deploys version 1.0 of the masterb3/website container (older version).
Also runs 4 replicas of the application.
Labeled as release: v2, representing the alternative deployment.
Uses the same resource limits as the blue deployment.