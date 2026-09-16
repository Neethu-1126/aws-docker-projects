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
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKERHUB_USER',
                    passwordVariable: 'DOCKERHUB_TOKEN'
                )]) {
                    sh '''
                        echo "$DOCKERHUB_TOKEN" | docker login -u "$DOCKERHUB_USER" --password-stdin
                        docker push neethunivu/my-docker-webapp:latest
                        docker logout
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    docker pull neethunivu/my-docker-webapp:latest
                    docker rm -f jenkins-deployed-web || true
                    docker run -d --name jenkins-deployed-web -p 8084:80 neethunivu/my-docker-webapp:latest
                '''
            }
        }
    }
}
