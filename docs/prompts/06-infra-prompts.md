---
title: Infrastructure Prompts
nav_order: ""
description: Prompt examples and patterns for infrastructure-related tasks like DevOps, containerization, and deployment.
tags:
  - infrastructure
  - prompts
  - vibe coding
layout: default
---
# 🛰️ Infrastructure & Deployment Prompts

This guide provides a cheat sheet for writing effective prompts for **Infrastructure and Deployment** tasks. This is the "DevOps" layer of your project—it's about automating the processes that take your finished code and make it live, secure, and scalable on the internet.

Prompting for infrastructure involves creating the configuration files and scripts that define how your application is built, tested, containerized, and deployed. These are often the most critical prompts for ensuring a reliable and professional application.

---
### 1. CI/CD Pipeline Configuration

This is about creating the **Continuous Integration/Continuous Deployment (CI/CD)** workflow. It's an automated assembly line that runs every time you push code to your Git repository, ensuring quality and automating deployments.

* #### Basic Prompt:
    > Make a CI/CD pipeline.

* #### Specific Prompt:
    > Generate a **GitHub Actions** workflow file (`.github/workflows/main.yml`). The workflow must trigger on every push to the `main` branch. It should define the following sequential jobs:
    > 1.  **Lint & Test:** Check out the code, set up **Node.js version 20**, install dependencies with `npm ci`, and run the linter and test suite with `npm test`.
    > 2.  **Build:** If tests pass, build the application for production with `npm run build`.
    > 3.  **Deploy:** If the build succeeds, deploy the application to **Vercel** using the official Vercel CLI Action, using secrets for the organization ID, project ID, and auth token.

* #### Why It's Better:
    The specific prompt defines the **CI/CD provider** (GitHub Actions), the **trigger event** (push to main), and a **precise, sequential list of jobs** with their dependencies. It results in a robust, professional automation pipeline.

* #### 🛠️ Tool Examples:
    * **1. General-Purpose AI Code Assistants (Inside Your Editor)**
        * These tools assist you as you are actively writing the pipeline's configuration file (e.g., `.github/workflows/main.yml`). They are excellent for syntax, boilerplate, and suggesting individual steps.
        * **`GitHub Copilot`**: The industry standard. It provides real-time, line-by-line suggestions and can complete entire jobs based on the context of your file.
        * **`Cursor`**: Because it has full-project context, it can be prompted to create a pipeline that is aware of other scripts or files in your repository (e.g., "create a deployment step that runs the `deploy.sh` script").
        * **`Tabnine`**: Can be trained on your team's existing infrastructure scripts to learn and suggest commands and configurations that match your internal best practices.
        * **`Amazon CodeWhisperer`**: Particularly strong if your CI/CD pipeline needs to interact with AWS services, as it's trained on the AWS APIs.

    * **2. Advanced AI Chat & Generation Models (For Generating Complete Files)**
        * These large language models are best for taking a complex, high-level prompt and generating the entire, complete workflow file from scratch, which you can then copy and refine.
        * **`Claude 3 (Opus)`**: Its large context window makes it excellent for understanding complex requirements and generating very long, detailed configuration files.
        * **`GPT-4o (OpenAI)`**: Has strong reasoning capabilities and can often generate not only the YAML configuration but also the external scripts that the pipeline might need to call.
        * **`Google's Gemini Models`**: Useful if your pipeline is part of the Google Cloud ecosystem, as it has deep knowledge of `gcloud` commands and services.

    * **3. Platform-Integrated AI Assistants (Built into the CI/CD Tool Itself)**
        * These are AI features that the CI/CD platforms are building directly into their own products to help users create and debug pipelines without leaving their website.
        * **`GitLab Duo AI`**: GitLab's integrated suite of AI tools. It includes a "CI/CD component generator" and can help explain pipeline errors and suggest fixes directly within the GitLab interface.
        * **`GitHub's Built-in AI features`**: GitHub is progressively integrating Copilot more deeply into its platform, including features to help suggest and validate GitHub Actions workflows as you create them.
        * **`CircleCI / Jenkins AI Plugins`**: Other major CI/CD platforms are also integrating AI through official or community-built plugins to assist with configuration and troubleshooting.

    * **4. AI-Powered Analysis & Security Tools (For Improving Pipelines)**
        * These tools don't generate the pipeline but use AI to analyze it for errors, security vulnerabilities, and inefficiencies.
        * **`Snyk IaC`**: A security tool that can scan your CI/CD configuration files (like GitHub Actions workflows or Terraform files) for misconfigurations that could lead to security breaches.
        * **`Datadog AI`**: A monitoring platform that uses AI to analyze the performance and logs from your CI/CD runs to detect anomalies or suggest optimizations to make your pipelines faster and more reliable.

---
### 2. Containerization (Docker)

This is about creating a "shipping container" for your application using **Docker**. This ensures your application runs the exact same way on your laptop, your teammate's laptop, and on the final production server.

* #### Basic Prompt:
    > Dockerize my Node.js app.

* #### Specific Prompt:
    > Create an optimized, multi-stage `Dockerfile` for a production **Next.js** application.
    > - The first stage, named `builder`, should use a **Node.js 20** base image, install dependencies with `npm ci`, and build the application with `npm run build`.
    > - The final, smaller stage should use a minimal base image (like `node:20-alpine`), copy only the necessary built files from the `builder` stage (the `.next` directory, `public`, `node_modules`, and `package.json`), and define the final command to run the app in production mode (`npm start`).

* #### Why It's Better:
    It specifies a critical best practice **(multi-stage builds)** to create a smaller, more secure final image. It names the **exact files and folders** to include, resulting in a production-ready container.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`, `Docker's official AI tools`

---
### 3. Infrastructure as Code (IaC)

This is about defining your cloud resources (servers, databases, networks) in configuration files rather than manually clicking around in a web dashboard. This makes your infrastructure version-controlled, repeatable, and transparent.

* #### Basic Prompt:
    > I need an AWS server.

* #### Specific Prompt:
    > Using **Terraform**, write a configuration file to provision a basic web server on **AWS**. The configuration must:
    > 1.  Define the AWS provider for the `us-east-1` region.
    > 2.  Create a new Virtual Private Cloud (VPC) with a public subnet.
    > 3.  Launch a single `t2.micro` EC2 instance running the latest Ubuntu Server AMI.
    > 4.  Assign a security group to the instance that allows inbound TCP traffic on port `80` (HTTP) and `22` (SSH) from anywhere.

* #### Why It's Better:
    It specifies the **IaC tool** (Terraform), the **cloud provider** (AWS) and **region**, the **exact resources** to create (VPC, EC2), and the **specific configuration details** (instance type, OS, security rules).

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`, `Pulumi AI`

---
### 4. Environment & Secrets Management

This covers the secure handling of sensitive information like API keys, database credentials, and other configuration that changes between development and production environments.

* #### Basic Prompt:
    > How do I use my secret key?

* #### Specific Prompt:
    > Show me the complete workflow for handling a `STRIPE_API_KEY` in a **Vercel** deployment for a **Next.js** app.
    > 1.  Show the command to add the key as a **production environment variable** using the **Vercel CLI**.
    > 2.  Show the Node.js code for securely accessing this variable inside a Next.js API route using `process.env.STRIPE_API_KEY`.
    > 3.  Add a check to the application's startup process that throws an error if the server is started in production mode and this variable is not defined.

* #### Why It's Better:
    It asks for a complete, end-to-end workflow: **how to set the secret** with a specific tool, **how to access it** in code, and a **best practice for validation** to prevent production failures.

* #### 🛠️ Tool Examples:
    `GitHub Copilot`, `Cursor`, `Phind`

---
### ✅ Summary Cheat Sheet

| Prompting For... | Key Details to Include in Your Prompt | Example Tools |
| :--- | :--- | :--- |
| **CI/CD Pipelines** | CI/CD Provider (GitHub Actions), trigger event (e.g., push to `main`), and a sequential list of jobs with their commands. | `GitHub Copilot`, `Cursor`, `GitLab Duo AI` |
| **Containerization** | The application type (Node.js, etc.), best practices (multi-stage builds), and optimization goals (e.g., small image size). | `GitHub Copilot`, `Docker's AI tools` |
| **Infrastructure as Code** | The IaC tool (Terraform), cloud provider (AWS), and the exact resources and configurations to create. | `GitHub Copilot`, `Pulumi AI`|
| **Secrets Management** | The platform (Vercel, etc.), the variable name, the method for setting it, and the code for accessing and validating it. | `GitHub Copilot`, `Cursor` |
```