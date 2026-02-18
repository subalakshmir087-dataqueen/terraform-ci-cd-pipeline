pipeline {
    agent any

    environment {
        GIT_SSH_COMMAND = "ssh -i /var/lib/jenkins/.ssh/id_ed25519 -o UserKnownHostsFile=/var/lib/jenkins/.ssh/known_hosts -o StrictHostKeyChecking=yes"
    }

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'git@github.com:subalakshmir087-dataqueen/terraform-ci-cd-pipeline.git'
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
    } // closes stages
} // closes pipeline

