Kubernetes Deployment for MyWebApp & MasterWebApp
--------------------------------------------------------------------------------
This repository contains Kubernetes manifests to deploy two web applications: mywebapp and masterwebapp.

Features
MyWebApp Deployment:

Deploys 5 replicas using a Recreate strategy.
Runs the container image masterb3/php-app.
Exposed via a Service (mywebappsvclb) on port 8090.
MasterWebApp Deployment:

Deploys 5 replicas using a RollingUpdate strategy (max 3 new pods at a time, 1 unavailable).
Runs the container image masterb3/website:1.0.