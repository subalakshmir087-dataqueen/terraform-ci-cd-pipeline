pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main',  // <- explicitly use 'main'
                    url: 'git@github.com:subalakshmir087-dataqueen/terraform-ci-cd-pipeline.git',
                    credentialsId: 'github-ssh-key'
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
