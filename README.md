# React Vite Project – CI/CD with GitHub Actions

This repository contains a **React application built with Vite**, integrated with a **full Jenkins-like CI/CD pipeline** using **GitHub Actions reusable workflows**.  
The project demonstrates an **end-to-end DevOps workflow** from code commit to Kubernetes deployment.

---

## 🚀 CI/CD Overview

The CI/CD pipeline automates the complete application lifecycle:

1. Code commit or pull request
2. Continuous Integration (CI)
3. Unit testing and code quality checks
4. Docker image build and push
5. Helm chart packaging
6. Continuous Deployment (CD) to Kubernetes

All CI and CD logic is implemented using **reusable workflows** stored in a separate repository.

---

## 🔧 Technologies Used

- React + Vite
- GitHub Actions
- Reusable Workflows (`workflow_call`)
- SonarCloud
- Docker & DockerHub
- Kubernetes
- Helm
- Self-hosted GitHub Runner

---

## 🔁 CI Pipeline

### Trigger
- `push` to `main`
- `pull_request`

### CI Responsibilities
- Checkout source code
- Install dependencies
- Run unit tests (Vitest)
- Perform code quality analysis (SonarCloud Quality Gate)
- Build and push Docker image
- Lint and package Helm chart
- Upload Helm artifacts

The CI pipeline **calls a reusable workflow** from the `react-cicd-templates` repository.

---

## 🚢 CD Pipeline

### Trigger
- Automatically triggered after successful CI completion

### CD Responsibilities
- Download Helm artifacts from CI
- Authenticate with Kubernetes cluster
- Deploy application using Helm
- Manage application releases

The CD pipeline **calls a reusable workflow** from the `react-cicd-templates` repository.

