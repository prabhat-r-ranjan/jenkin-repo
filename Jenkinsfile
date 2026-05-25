pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t jenkins-demo-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f jenkins-demo-container || exit 0'
                bat 'docker run -d --name jenkins-demo-container -p 9090:80 jenkins-demo-app'
            }
        }
    }
}