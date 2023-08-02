pipeline {   
   environment {
         AWS_SECRET_KEY_ID     = credentials('AWS_SECRET_KEY_ID')
         AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
   }
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
