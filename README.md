## Purpose

This repository contains a test application implemented in Go. The application is designed to post system metrics to a metrics endpoint, primarily for testing the Telegraf operator. The application leverages the Prometheus procfs package to gather system metrics.

## Deploying to Kubernetes

You can deploy the application to a Kubernetes cluster using the provided YAML file. Replace <your-docker-image> with the full path of your Docker image in the Google Cloud Artifact Registry.
yaml
## Troubleshooting

If your deployment is in a crash backoff loop with the error "exec ./app: exec format error", it means that the binary file your container is trying to execute is not compatible with the architecture of the system where the container is running. Make sure the GOARCH environment variable in the Dockerfile matches the architecture of your deployment target.

If the Telegraf operator is not attaching a sidecar to your deployment, check if the Telegraf operator is running, check the annotations in your deployment, check the logs of the Telegraf operator, and check the Telegraf operator configuration.