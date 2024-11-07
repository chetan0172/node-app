pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://bitbucket.org/your_username/your_repo.git', branch: 'main'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t hello-world-app .'
                }
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    // Log in to Docker Hub or your private registry if needed
                    sh 'docker tag hello-world-app your_dockerhub_username/hello-world-app'
                    sh 'docker push your_dockerhub_username/hello-world-app'
                }
            }
        }
    }
}