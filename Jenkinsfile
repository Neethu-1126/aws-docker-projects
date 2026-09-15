pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t neethunivu/my-docker-webapp:latest .'
            }
        }

        stage('Test') {
            steps {
                sh 'docker image inspect neethunivu/my-docker-webapp:latest'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                sh 'docker push neethunivu/my-docker-webapp:latest'
            }
        }
    }
}
