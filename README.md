# Jenkins-CICD-Pipeline-Project
# Jenkins Pipeline for Java-Based Application using Maven, SonarQube, Argo CD, Helm, and Kubernetes

![Screenshot 2023-03-28 at 9 38 09 PM](https://user-images.githubusercontent.com/43399466/228301952-abc02ca2-9942-4a67-8293-f76647b6f9d8.png)

This project outlines the step-by-step setup of an end-to-end Jenkins pipeline for a Java application using Maven, SonarQube, Helm, Argo CD, and Kubernetes.

---

## Prerequisites

- Java application code hosted in a Git repository  
- Jenkins server (with necessary plugins)  
- Kubernetes cluster  
- Helm package manager  
- Argo CD for GitOps deployment  

---

## 🔧 Steps to Set Up the Pipeline

### 1. **Install Required Jenkins Plugins**
- Git Plugin  
- Maven Integration Plugin  
- Pipeline Plugin  
- Kubernetes Continuous Deploy Plugin  

### 2. **Create a New Jenkins Pipeline**
- In Jenkins, create a new Pipeline job.
- Configure it with your Git repository URL for the java application.
- Add a `Jenkinsfile` to your repo to define the pipeline stages.

### 3. **Define the Pipeline Stages**

- **Stage 1**: Checkout source code from Git  
- **Stage 2**: Build the Java app using Maven  
- **Stage 3**: Run unit tests using JUnit and Mockito  
- **Stage 4**: Analyze code quality with SonarQube  
- **Stage 5**: Package the app as a JAR file. 
- **Stage 6**: Deploy the app to a test environment using Helm
- **Stage 7**: Run user acceptance tests on the deployed application.
- **Stage 8**: Promote the app to production using Argo CD  

### 4. **Configure Jenkins Pipeline Stages**
Each stage in the pipeline is configured using plugins/tools as follows:

- **Checkout** – Git Plugin  
- **Build** – Maven Plugin  
- **Unit Testing** – JUnit & Mockito  
- **SonarQube Scan** – SonarQube Plugin  
- **Packaging** – Maven Plugin (creates JAR)  
- **Test Deployment** – Kubernetes Deploy plugin + Helm  
- **UAT** – Testing framework like Selenium  
- **Production Deployment** – Argo CD
  
    Stage 1: Use the Git plugin to check out the source code from the Git repository.
    Stage 2: Use the Maven Integration plugin to build the Java application.
    Stage 3: Use the JUnit and Mockito plugins to run unit tests.
    Stage 4: Use the SonarQube plugin to analyze the code quality of the Java application.
    Stage 5: Use the Maven Integration plugin to package the application into a JAR file.
    Stage 6: Use the Kubernetes Continuous Deploy plugin to deploy the application to a test environment using Helm.
    Stage 7: Use a testing framework like Selenium to run user acceptance tests on the deployed application.
    Stage 8: Use Argo CD to promote the application to a production environment.
---

## 🚀 Argo CD Setup

- Install Argo CD in your Kubernetes cluster  
- Create a Git repo to store your Helm charts and Kubernetes manifests  
- Write a Helm chart for your Java app (with manifests & values)  
- Add the Helm chart to the repo Argo CD is monitoring  

---

## 🔗 Integrating Jenkins pipelines with Argo CD

- Add Argo CD API token to Jenkins credentials  
- In your `Jenkinsfile`, include a deployment stage that triggers Argo CD using its API  

---

## ▶️ Running the Pipeline

- Trigger the Jenkins pipeline manually or via webhook  
- Monitor each stage’s execution  
- Troubleshoot and fix any issues during the run  

---

## ✅ Summary

This Jenkins pipeline provides full CI/CD automation for a Java application—from Git commit to production deployment—using:

- **Jenkins** for automation  
- **Maven** for building  
- **SonarQube** for quality analysis  
- **Helm** & **Kubernetes** for deployment  
- **Argo CD** for GitOps-based delivery

