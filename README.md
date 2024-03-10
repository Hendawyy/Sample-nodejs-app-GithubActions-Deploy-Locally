# Simple Node Application Using CI/CD Pipeline. 

🚀 Sample Node Hello World Application Using CI/CD Pipeline (GitHub Actions).

Deploying The Application locally on minikube ☸.

## Table of Contents

- [Simple Node Application Using CI/CD Pipeline.](#simple-node-application-using-cicd-pipeline)
  - [Table of Contents](#table-of-contents)
  - [🛠️ Prerequisites:](#️-prerequisites)
  - [Introduction:](#introduction)
  - [Application Setup:](#application-setup)
  - [CI Pipeline:](#ci-pipeline)
  - [Deployment:](#deployment)
  - [Monitoring and Logging:](#monitoring-and-logging)

##  🛠️ Prerequisites:

    - Docker  🐋
    - Kubectl ☸
    - minikube ☸
    - Terraform 🏗️
    - 
## Introduction:

👋 Welcome to the Sample Node App! In this project we will Dockerize the provided node app, and deploy it on a cluster using The CI/CD pipeline GitHub Actions.

## Application Setup:

    - Fork the provided simple web application [repository](https://github.com/johnpapa/node-hello) (e.g., a basic "Hello World"app in Node.js) 🍴.
    - Containerize the application by creating a Dockerfile 🐋.

## CI Pipeline:
Set up a CI/CD pipeline using GitHub Actions. 
1. You need to create a directory `.github/workflows` and add your CI/CD configuration file.
    ```
        mkdir -p .github/workflows
    ```
2. Create the configuration file and name it whatever, I named it `ci.yml`.
    ```
        cd .github/workflows/
        touch ci.yml
    ```
Inside The `ci.yml` file
    - Name your pipeline like this:
            ```
                name: CI Pipeline
            ```
    - Specify The triggering conditions for running the workflow (e.g., push or pull request) and you will also need to specify the branch.
            ```
                on:
                push:
                    branches: [master]
                pull_request:
                    branches: [master]
            ```
    - Then you need to specify the key `jobs` then name your `job` and add the `steps` for this job.
The pipeline should automate the following:
- Linting the code.
  - Add The Job and push which will trigger the workflow to run 
     > [!NOTE]
     > I used the `Super Linter` action which is available in marketplace.
    
- Building the Docker container.
- Pushing the container to a container registry (Docker Hub)

## Deployment:
    Deploy the application using Terraform:
    - Run the container locally using the docker provider.
    - Deploy the container on a container orchestration platform (e.g. minikube).

## Monitoring and Logging:
    Set up log aggregation for the application using the free tier on New Relic.