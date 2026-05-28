pipeline {

    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/your-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t yourdockerhub/kravix-project:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push yourdockerhub/kravix-project:v1'
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