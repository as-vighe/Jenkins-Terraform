pipeline {
    parameters{
        booleanParam(name: 'autoApprove',defaultvalue: 'false',description: 'Automatically run after apply generating plan?')
  }
    environment{
         AWS_SECRET_KEY_ID = credentials('AWS_SECRET_KEY_ID')
         AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
  }
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', credentialsId: '<CREDS>', url: 'https://github.com/as-vighe/Jenkins-Terraform'
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
