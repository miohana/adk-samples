# Deployment Guide

This directory contains scripts to deploy the High-Volume Document Analyzer Agent to Google Cloud Vertex AI Agent Engine.

## Prerequisites

1.  **Google Cloud Project:** Ensure you have a GCP project with Vertex AI API enabled.
2.  **Authentication:** Authenticate your local environment:
    ```bash
    gcloud auth application-default login
    ```
3.  **Staging Bucket:** You need a GCS bucket to stage the agent's artifacts.

## Deployment with Python

The `deploy_agent.py` script automates the deployment process using the Vertex AI SDK.

1.  **Configure Environment:**
    Ensure your `.env` file (in the root of the agent directory) has the following variables:
    ```env
    GOOGLE_CLOUD_PROJECT="your-project-id"
    GOOGLE_CLOUD_LOCATION="us-central1"
    STAGING_BUCKET="gs://your-staging-bucket"
    ```

2.  **Run the script:**
    ```bash
    uv run python deploy/deploy_agent.py
    ```

The script will create a new Agent Engine resource (or update an existing one if `.agent_engine_resource.json` is present) and output the resource name.
