Kubernetes PostgreSQL Deployment
-----------------------------------------
This repository provides a StatefulSet deployment of PostgreSQL with persistent storage and configuration management.

Features
----------------
Persistent Storage:
A PersistentVolume (postgresdb-pv) and PersistentVolumeClaim (postgres-pvc) ensure 1Gi of storage is available at /data/postgresql.

Configuration Management:

A ConfigMap (postgres-config) sets environment variables for the database (POSTGRES_DB, POSTGRES_USER, POSTGRES_PASSWORD).

StatefulSet Deployment:

Runs PostgreSQL 13.18 with 1 replica, ensuring data persistence.
Uses a hostPath volume for local storage.