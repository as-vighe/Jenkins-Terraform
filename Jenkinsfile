pipeline {   
    environment {
         AWS_SECRET_KEY_ID     = credentials('aws_user')
         AWS_SECRET_ACCESS_KEY = credentials('aws_user')
   }
    agent any
    stages {
        stage('test AWS credentials') {
            steps {
                withAWS(credentials: 'aws_user', region: 'us-east-1'){
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
