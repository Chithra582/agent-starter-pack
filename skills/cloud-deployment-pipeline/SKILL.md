---
name: cloud-deployment-pipeline
description: Use when configuring cloud infrastructure, Terraform manifests, and CI/CD pipelines targeting Google Cloud.
---

# Cloud Deployment Pipeline

## Overview
Configures infrastructure-as-code, Docker containers, and Cloud Build CI/CD automation to deploy agents to Cloud Run, Vertex AI, or GKE.

## When to Use
- When deploying scaffolded agent applications to Google Cloud production environments.
- When configuring automated build triggers on pull requests via Cloud Build or GitHub Actions.
- When provisioning IAM service accounts, secret bindings, and artifact repositories.

## Core Capabilities
1. **Multi-Target Deployment**: Generates configurations for Cloud Run (serverless container) or Vertex AI Reasoning Engine.
2. **Infrastructure as Code**: Emits production-tested Terraform templates with least-privilege IAM policies.
3. **Automated CI/CD**: Cloud Build workflows handling automated testing, container builds, and deployment stages.
