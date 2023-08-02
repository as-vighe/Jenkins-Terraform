pipeline {   
    agent any
    stages {
        stage('test AWS credentials') {
            steps {
                withAWS(credentials: 'AWS_SECRET_ACCESS_KEY', region: 'us-east-1')
            }
        }
        stage('Checkout') {
            steps {
                git 'https://github.com/as-vighe/Jenkins-Terraform'
            }
        }
        stage('Terraform init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Terraform apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
        
    }
}
