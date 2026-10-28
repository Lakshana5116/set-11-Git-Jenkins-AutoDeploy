pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Lakshana5116/set-11-Git-Jenkins-AutoDeploy.git'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                bat 'kubectl get deployment set11-web'
                bat 'kubectl get pods -l app=set11-web'
            }
        }
    }
}