# Jenkins-CI-CD-pipeline-for-a-Flask-web-app

# Flask CI/CD with Jenkins

A minimal Flask app with Jenkins pipeline to build Docker image and deploy to remote Ubuntu server.

## Files
- app.py : Flask app
- Dockerfile : Docker image
- Jenkinsfile : Jenkins Declarative pipeline

## Quick start
1. Configure Jenkins with SSH credentials and a pipeline job pointing to this repo.
2. Ensure remote server has Docker installed and SSH public key added.
3. Push commits to `main` to trigger CI/CD.
