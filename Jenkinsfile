pipeline {

    agent any

    stages {

        stage('Clone Code') {
            steps {
               git 'https://github.com/Lahari268/kravix-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t laharikalva/kravix-project:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push laharikalva/kravix-project:v1'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
                sh 'kubectl apply -f ingress.yaml'
            }
        }
    }
}
