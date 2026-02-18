pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'git@github.com:yourusername/terraform-ci-cd-pipeline.git'
            }
        }
        stage('Build Docker') {
            steps {
                sh 'docker build -t my-app .'
            }
        }
        stage('Run Docker') {
            steps {
                sh 'docker run -d -p 8080:8080 my-app'
            }
        }
    }
}
