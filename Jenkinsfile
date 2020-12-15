pipeline {
    agent { label'docker-agent'  }
    stages {
        stage('Clone source code') {
            steps {
                git 'https://github.com/handuy/nodejs-mongodb'
            }
        }
    }
    stages {
        stage('Build image with Dockerfile') {
            steps {
                docker build -t demo-service .
            }
        }
    }
    stages {
        stage('Build app with docker-compose') {
            steps {
                docker-compose up -d
            }
        }
    }
}