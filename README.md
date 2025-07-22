# Comprehensive CI/CD Pipeline on AWS

---

### Introduction
This repository showcases a **small-scale, end-to-end Continuous Integration and Continuous Delivery (CI/CD) pipeline** built entirely with Amazon Web Services (AWS). Rather than a single, monolithic project, it is structured into **six, modular components**, each focusing on a fundamental stage or critical service within the modern CI/CD lifecycle.

These projects were completed to demonstrate hands-on experience in automating software delivery, from source code management and dependency handling to robust building, testing, and deployment across various AWS services. Each module is designed for clarity, providing insights into its specific role and contribution to the overall automated workflow.

---

### Projects Included

This repository contains the following CI/CD projects, each with its own dedicated folder and architecture diagram:

* **[Launch EC2](Launch-EC2/)**
    * Details launching and configuring an AWS EC2 instance, demonstrating foundational cloud compute setup often used as a target environment for deployments.
* **[Connect-GitHub](Connect-GitHub/)**
    * Outlines the secure integration of GitHub with AWS services, enabling automated triggers for CI/CD pipelines based on code changes.
* **[CodeArtifact](CodeArtifact/)**
    * Explores setting up and utilizing AWS CodeArtifact for centralized package management, ensuring consistent dependency handling and reproducibility across builds.
* **[CodeBuild](CodeBuild/)**
    * Focuses on the core build and test phase using AWS CodeBuild, covering `buildspec.yml` configuration for compilation, unit testing, and artifact generation.
* **[CodeDeploy](CodeDeploy/)**
    * Demonstrates automated application deployment to various compute services (e.g., EC2) using AWS CodeDeploy, ensuring controlled and efficient software releases.
* **[CodePipeline](CodePipeline/)**
    * Orchestrates all preceding stages into a cohesive, automated CI/CD workflow, defining the entire release process from source changes to final deployment.

---

### Technologies & Services Used

* **Cloud Platforms:** AWS (EC2, S3, IAM, VPC, CodePipeline, CodeBuild, CodeDeploy, CodeArtifact, CloudWatch, CloudFormation, CodeConnection)
* **Tools:** GitHub, Git
* **Concepts:** Continuous Integration, Continuous Delivery, Automation, Dependency Management, Build Automation, Deployment Strategies, Secure Access Control.

---

## Learning Objectives

-   Design and implement end-to-end automated software delivery pipelines.
-   Configure and integrate core AWS DevOps services (CodePipeline, CodeBuild, CodeDeploy, CodeArtifact).
-   Manage source code versioning and artifact flow efficiently.
-   Automate the build, test, and deployment processes for various application types.
-   Understand the orchestration and dependencies within a multi-stage CI/CD workflow.

---

### How to Explore

Each project has its own dedicated folder containing a detailed `README.md` with an architecture diagram, specific technologies used, key concepts demonstrated, and steps taken for implementation. Feel free to navigate through them to understand each part of the pipeline!

---

### Architecture

