# Ansible Docker CI/CD Project

## Overview

This project demonstrates how to automate the deployment of a simple Flask application using **Ansible**, **Docker**, and **GitHub Actions** for **CI/CD**. It includes setting up Docker containers for the application and using GitHub Actions to automate the deployment on every code push to the main branch.

## Project Structure

ansible-docker-cicd/ ├── .github/ │ └── workflows/ │ └── ci.yml # GitHub Actions workflow for CI/CD ├── app.py # Simple Flask app ├── Dockerfile # Dockerfile to containerize the Flask app ├── deploy.yml # Ansible playbook to manage the Docker container ├── hosts.ini # Ansible inventory file for targeting localhost ├── requirements.txt # Python dependencies for the Flask app └── README.md # Project description and setup instructions


## Technologies Used
- **Ansible**: Automation tool for configuration management and application deployment.
- **Docker**: Platform for developing, shipping, and running applications in containers.
- **GitHub Actions**: Continuous Integration/Continuous Deployment (CI/CD) tool to automate workflows.
- **Flask**: Python micro web framework used for the demo application.

## Requirements

To run this project locally, you will need:
- Python 3.10+
- Docker installed
- Ansible installed

## Setup and Usage

### 1. Clone the repository

```bash
git clone https://github.com/sofian-30/ansible-docker-cicd.git
cd ansible-docker-cicd

 2. Install dependencies
Create and activate a Python virtual environment, then install the required dependencies:
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

3. Run the Ansible Playbook
Ensure Docker is installed and running on your machine. Then, use the following command to run the Ansible playbook, which will set up Docker and deploy the Flask application:
ansible-playbook -i hosts.ini deploy.yml --ask-become-pass

This will:

Ensure Docker is installed.
Start the Docker service.
Build and run the Flask application inside a Docker container.
4. Access the Flask App
Once the playbook is successfully executed, the Flask app will be running in a Docker container. You can access it at http://localhost:5000.

5. Continuous Integration and Deployment (CI/CD)
A GitHub Actions workflow has been set up to automatically:

Run the Ansible playbook in test mode.
Build the Docker image.
Run the Docker container on every push to the main branch.
You can view the CI/CD status in the Actions tab of the GitHub repository.

Project Workflow
Local Setup: Clone the repo, install dependencies, and use Ansible to deploy the application locally using Docker.
CI/CD: Push changes to GitHub to trigger automated builds and deployments via GitHub Actions.


Une fois cela fait, tu pourras ajouter ce fichier à ton dépôt et le pousser sur GitHub avec les commandes suivantes :

```bash
git add README.md
git commit -m "Add README to the project"
git push origin main
