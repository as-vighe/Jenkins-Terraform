pipeline {   
    agent any
    stages {
        stage('test AWS credentials') {
            steps {
                withAWS(credentials: 'AWS_ACCESS_KEY_ID', region: 'us-east-1'){
                    sh 'aws iam get-user'
                }
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
