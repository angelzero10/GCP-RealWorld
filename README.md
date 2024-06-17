# Terraform GCP Infrastructure Project
## Overview
This project sets up a minimal-cost infrastructure on Google Cloud Platform (GCP) using Terraform. It includes a Google Kubernetes Engine (GKE) cluster and a Cloud Storage bucket, with professional naming conventions and best practices for handling sensitive information.

## Prerequisites
- Terraform installed
- A Google Cloud Platform (GCP) account

## Setup Instructions
1. Create and Download Service Account Key
2. Set Up Environment Variables
     - Export the environment variables for Terraform to use:

```
export TF_VAR_credentials_file="<path-to-service-account-key>.json"
export TF_VAR_project="<your-gcp-project-id>"
export TF_VAR_region="us-central1"
```

3. Initialize and Apply Terraform Configuration
Initialize Terraform:

```
terraform init
```
Apply the Terraform configuration:
```
terraform apply
```
Follow the prompts and confirm the changes to create the infrastructure.

4. Connect to Your GKE Cluster
 - Authenticate with your GKE cluster:
```
gcloud container clusters get-credentials personal-project-cluster --region us-central1 --project <your-gcp-project-id>
```

Deploy your application to the GKE cluster using Kubernetes configuration files.

For Handling Sensitive Information: 
- Use Environment Variables: Pass sensitive information such as credentials and API keys using environment variables.
- Store State Files Remotely: Use a remote backend like GCP Cloud Storage to store Terraform state files.