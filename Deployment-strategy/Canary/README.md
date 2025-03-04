Kubernetes Deployment: Canary Deployment Strategy
This Kubernetes setup defines a canary deployment strategy, allowing gradual rollout and testing of a new application version while keeping the stable version in production.

Overview
The setup includes:

Two Deployments

myprofilev1: Runs version 1 of the application (masterb3/website:1.0).
myprofilev2: Runs a newer version (masterb3/php-app).
Each deployment has three replicas to ensure high availability.
Resource limits per container: 128Mi memory and 500m CPU.
Two Services

canarylb: Exposes myprofilev1 using NodePort, serving as the main stable version.
validatev2: Exposes myprofilev2, allowing selective traffic routing for testing purposes.
Purpose
This setup enables canary deployment, where:

myprofilev1 remains the primary, stable version in production.
myprofilev2 can be tested in a controlled manner before a full rollout.
This approach helps in identifying potential issues in the new version (myprofilev2) before replacing myprofilev1 entirely, reducing risks and improving deployment reliability.