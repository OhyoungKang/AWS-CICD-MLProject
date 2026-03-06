## End-to-End Machine Learning Project (MLOps + CI/CD)

This project demonstrates a complete end-to-end machine learning pipeline with automated deployment using GitHub Actions and AWS infrastructure.

The workflow includes model training, Docker containerization, CI/CD pipeline configuration, and deployment to an AWS EC2 instance.

## Project Workflow

The CI/CD pipeline follows this architecture:

GitHub → GitHub Actions → Docker Build → AWS ECR → EC2 Deployment

## Steps Implemented
	1.	Docker build and containerization
	2.	GitHub Actions CI/CD workflow
	3.	AWS IAM user configuration
	4.	AWS ECR container registry setup
	5.	EC2 self-hosted runner deployment

## Docker Setup on EC2

Commands to install Docker on the EC2 instance.

### Optional updates

sudo apt-get update -y
sudo apt-get upgrade -y

### Install Docker

curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

### Allow Docker usage without sudo

sudo usermod -aG docker ubuntu
newgrp docker

## Configure EC2 as Self-Hosted Runner
	1.	Go to GitHub Repository → Settings → Actions → Runners
	2.	Add a new self-hosted runner
	3.	Run the provided setup commands on the EC2 instance.

## GitHub Secrets Configuration

Add the following secrets in:

Repository → Settings → Secrets → Actions

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY

AWS_REGION = ap-northeast-2

AWS_ECR_LOGIN_URI = 

Example:

566373416292.dkr.ecr.ap-northeast-2.amazonaws.com

ECR_REPOSITORY_NAME = mlproject

## Technologies Used

Python
Scikit-learn
Flask
Docker
GitHub Actions
AWS ECR
AWS EC2

## Author

Ohyoung Kang
AI Engineer | MLOps | AI Infrast

GitHub: https://github.com/OhyoungKang
LinkedIn: https://www.linkedin.com/in/ohyoung-kang-6058bb240/

## Acknowledgement

This project was originally inspired by an online coursework example.

The implementation was extensively re-engineered into a production-style 
MLOps system with automated CI/CD pipelines, AWS-based container deployment, 
health monitoring endpoints, and operational logging designed 
for real-world deployment scenarios.
