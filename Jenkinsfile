pipeline {
    agent any
    stages {
        stage('Checkout From Git') {
            steps {
                git branch: 'prod' , url: 'https://github.com/bkrrajmali/terraform-aws-evening-jenkins.git'
            }
        }
    }
}