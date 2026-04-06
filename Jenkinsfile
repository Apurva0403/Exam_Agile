pipeline {
    agent any 

    stages {
        
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/Apurva0403/Exam_Agile.git'
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    
                    sh 'docker build -t pricelist-app:latest .'
                }
            }
        }

        
        stage('Push to Registry') {
            steps {
                echo 'Pushing image to Docker Hub...'
                
            }
        }

        
        stage('Deploy to K8s') {
            steps {
                echo 'Deploying to Kubernetes Cluster...'
                sh 'kubectl apply -f k8s-deployment.yaml'
            }
        }
    }
}
