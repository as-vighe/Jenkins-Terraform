pipeline {   
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/as-vighe/Jenkins-Terraform.git'
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
