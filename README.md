🎓 Docker-Swarm-Based-Multi-Service-College-Management-System-with-CI-CD
multi-service-College-Portal-with-Docker-Jenkins-CI-CD-and-worker-nodes.
📌 Project Overview

College-Portal is a containerized multi-service college management system designed to manage different departments and roles inside a campus environment.

This project demonstrates:

Microservices Architecture

Docker Swarm Cluster (Manager + Worker Nodes)

Jenkins CI/CD Pipeline

Automated Docker Image Build & Deployment

🏗️ System Architecture

🐳 Docker Swarm (1 Manager Node + 2 Worker Nodes)

🤖 Jenkins for CI/CD

📦 Docker Hub for Image Repository

🐙 GitHub for Source Code Management

👥 Services Included

👨‍🎓 Student Service

👩‍🏫 Teacher Service

🛡️ Security Service

🧹 Cleaning Staff Service

Each service runs as an independent container inside Docker Swarm.

⚙️ Technologies Used

Docker

Docker Swarm

Jenkins

GitHub

Linux 

Shell Scripting

Using your GitHub repo:
https://github.com/Ujwalkhairnar2004/Docker-Swarm-Based-Multi-Service-College-Management-System-with-CI-CD.git

🚀 CI/CD Pipeline

🔹 PUSH Pipeline (Build & Push Image)
PUSHING:

pipeline {
    agent any 
    
    stages {
        stage('checkout') {
            steps {
                git 'https://Docker-Swarm-Based-Multi-Service-College-Management-System-with-CI-CD.git'
            }
        }
        stage('build') {
            steps {
                sh 'docker build -t $img .'
            }
        }
        stage('tag') {
            steps {
                sh 'docker tag $img $repo'
            }
        }
        stage('push') {
            steps {
                sh 'docker login -u  -p 
                sh 'docker push $repo'
            }
        }
    }
}

Checkout source code from GitHub

Build Docker image

Tag Docker image

Push image to Docker Hub

🔹 DEPLOYMENT Pipeline

pipeline {
    agent any

    stages {
        stage('check') {
            steps {
                git 'https://Docker-Swarm-Based-Multi-Service-College-Management-System-with-CI-CD.git'
            }
        }
        stage('stack') {
            steps {
                sh 'docker stack deploy -c docker-compose.yml courses'
            }
        }
    }
}

Pull latest code

Deploy using Docker Stack

Run services in Docker Swarm cluster

🐳 Docker Swarm Setup
Initialize Swarm (Manager Node)
docker swarm init
Join Worker Nodes
docker swarm join --token <TOKEN> <MANAGER-IP>

<img width="1366" height="768" alt="{CCD8240F-039C-451C-A340-FD633BCE039A}" src="https://github.com/user-attachments/assets/c34d7cc2-bd9a-4f41-966e-fee0cb3e3849" />


🔐 Security Best Practice

⚠️ Do NOT hardcode Docker Hub username and password in Jenkins pipeline.
Use Jenkins Credentials Manager for secure authentication.

📈 Key Features

✔ Multi-Service Architecture
✔ Scalable using Docker Swarm
✔ CI/CD Automation with Jenkins
✔ Containerized Deployment
✔ Production-Oriented Setup

🔹 PUSH Pipeline (Build & Push Image)

 output :

 🔹 DEPLOYMENT Pipeline
 
 output :
 
👨‍💻 Author

Your Name
Ujwal Ganesh Khairnar 
