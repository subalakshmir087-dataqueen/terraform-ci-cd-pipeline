pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'git@github.com:subalakshmir087-dataqueen/terraform-ci-cd-pipeline.git',
                    credentialsId: 'd506eac9-7617-4f23-8cb6-728669d61220'
            }
        }

        stage('Check Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Build Docker') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Run Docker') {
            steps {
                sh 'docker run -d --name my-app-container my-app'
            }
        }
    }
}



