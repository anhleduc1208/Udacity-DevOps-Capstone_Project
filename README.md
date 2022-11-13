# Udacity-DevOps-Capstone_Project

The final project of the Cloud DevOps Engineer

## Table of contents

- [General info](#general-info)
- [Folder structure](#folder-structure)
- [Tools](#technologies)
- [Usage](#setup)
- [Result](#result)

## General info

The Application is based on a python3 script using <a target="_blank" href="https://flask.palletsprojects.com">flask</a> to render a simple webpage in the user's browser.
A requirements.txt is used to ensure that all needed dependencies come along with the Application.

## Tools

Project is created with:

- CirleCI
- CloudFormation
- AWS - EKS
- Kubernetes
- Docker Hub
- GitHub
- Ansible

## Folder structure

- src : Source Files
- .circleci : Configuration CircleCI Pipeline file
- cloudformation: contains Cloudformation IaC files that helps to create infra on AWS
- ansible: contains ansible config file to connect to EC2 on AWS and set up the app on EKS cluster

## Usage

To run this project in CircleCI, you have to:

- Fork the project to your Github Account
- Setup and Configure CirceCI account with Github and AWS Credentials
- Setup DockerHub account.
- AWS : create an IAM user and a ssh key
- Configure enviroment variables AWS_DEAFULT_REGION, AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, DOCKERHUB_PASSWORD, DOCKERHUB_USERNAME in your CircleCI account
- Change the build job from config.yml in order to include your DockerHub credentials, for example :

```
docker build -t thanhbao0390/nginx-hello .
docker tag nginx-hello:latest ${DOCKERHUB_USERNAME}/nginx-hello:latest
docker push thanhbao0390/nginx-hello

```

## Result

Public LoadBalancer DNS:
