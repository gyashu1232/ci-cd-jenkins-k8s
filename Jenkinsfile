pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/gyashu1232/ci-cd-jenkins-k8s.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('flask-cicd-app')
                }
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}