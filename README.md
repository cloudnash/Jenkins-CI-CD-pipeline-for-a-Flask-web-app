# Jenkins-CI-CD-pipeline-for-a-Flask-web-app

1. Flask CI/CD with Jenkins

A minimal Flask app with Jenkins pipeline to build Docker image and deploy to remote Ubuntu server.

2. Files
- app.py : Flask app
- Dockerfile : Docker image
- Jenkinsfile : Jenkins Declarative pipeline

3. Quick start
1. Configure Jenkins with SSH credentials and a pipeline job pointing to this repo.
2. Ensure remote server has Docker installed and SSH public key added.
3. Push commits to `main` to trigger CI/CD.

```
flask-ci-cd-jenkins/
├── app.py
├── requirements.txt
├── Dockerfile
├── README.md
├── .dockerignore
└── Jenkinsfile
```

This project demonstrates a simple CI/CD pipeline using Jenkins to deploy a Flask web application on AWS EC2.

The setup includes two instances:

Jenkins Master EC2 – controls and triggers the pipeline.
Jenkins Slave EC2 – runs Docker and hosts the deployed app.

When code is pushed to GitHub, Jenkins pulls the latest changes and executes the Jenkinsfile, which has three stages:

Checkout – clone the GitHub repository.

Build – build a Docker image for the Flask app.

Deploy – stop any old container and run the new one on port 80.

The result is a fully automated process where every code change is built and deployed through Jenkins onto the slave EC2 instance.


Challenges faced included setting up Jenkins agents, managing SSH keys, and Docker permissions.
