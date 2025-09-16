# MonolithicPythonapp
Project A: CI/CD for a Monolithic Python Application on AWS EC2

Overview
The goal is to create a fully automated workflow that takes a Python Flask application from a
GitHub repository, containerizes it using Docker, and deploys it onto an AWS EC2 server. The
entire process will be orchestrated by a Jenkins pipeline, and the server configuration will be
managed using Ansible.

Tools
OS: Centos Stream 9
Version Control: GitHub
CI/CD: Jenkins on ec2
Containerization: Docker
Configuration Management: Ansible
Cloud Platform: AWS (EC2)
Application: Python + Flask - https://github.com/naveensingh575/MonolithicPythonapp/

Workflow
1. Code Commit: A developer pushes new code or changes for the Flask application to a
designated branch in the GitHub repository.
2. Pipeline Trigger: A webhook triggers the Jenkins pipeline.
3. Containerize: Jenkins builds a new Docker image of the Flask application using a
4. Dockerfile present in the repository.
5. Push to Registry: The newly created Docker image is pushed to a container registry (like
Docker Hub or AWS ECR).
6. Deploy: Jenkins executes an Ansible playbook with the target EC2 server's IP address.
7. The playbook performs the following actions on the server:
8. Pulls the latest Docker image from the registry.
9. Stops and removes the currently running application container.
10. Starts a new container using the updated image.
