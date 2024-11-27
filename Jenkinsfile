pipeline {
    agent any
    stages {
        stage('Checkout From Git') {
            steps {
                git branch: 'prod' , credentialsId: 'git-cred', url: 'https://github.com/bkrrajmali/terraform-aws-evening-jenkins.git'
            }
        }
        stage('Terraform Version') {
            steps {
                script {
                    sh 'terraform version'
                }
            }
        }
        stage('Terraform Init') {
            steps {
                script {
                    sh 'terraform init'
                }
            }
        }
    }
}