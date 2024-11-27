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
        stage('Terraform Validate') {
            steps {
                script {
                    sh 'terraform validate'
                }
            }
        }
        stage('Terraform Plan') {
            steps {
                script {
                    sh 'terraform plan'
                }
            }
        }
        stage('Terraform apply') {
            steps {
                script {
                    sh 'terraform apply --auto-approve'
                }
            }
        }
        stage('Approve To Destroy') {
            steps {
                input message: 'Approve to Destroy', ok: 'Destroy'
            }
        }
        stage('Terraform Destroy') {
            steps {
                script {
                    sh 'terraform destroy --auto-approve'
                }
            }
        }
    }
}