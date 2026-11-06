
pipeline {
    agent any

    environment {
        IMAGE_NAME = 'jenkins-cicd-app'
        CONTAINER_NAME = 'jenkins-cicd-app'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building Docker image'
                sh 'docker build -t ${IMAGE_NAME}:latest .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running application tests'
                sh 'docker run --rm ${IMAGE_NAME}:latest npm test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application'
                sh 'docker rm -f ${CONTAINER_NAME} || true'
                sh 'docker run -d --name ${CONTAINER_NAME} -p 3001:3000 ${IMAGE_NAME}:latest'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD Pipeline failed. Check the console output.'
        }
    }
}
