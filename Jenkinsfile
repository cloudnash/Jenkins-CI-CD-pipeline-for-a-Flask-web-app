pipeline {
    agent { label 'docker-slave' }  // run on your slave EC2

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'git@github.com:cloudnash/YOUR_REPO.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker stop flask-app || true
                docker rm flask-app || true
                docker run -d --name flask-app -p 80:5000 flask-app:latest
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment successful! Visit http://172.31.28.120 to see app"
        }
        failure {
            echo "Build or deployment failed"
        }
    }
}
