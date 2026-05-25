pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-demo-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f jenkins-demo-container || exit 0'
                sh 'docker run -d --name jenkins-demo-container -p 9090:80 jenkins-demo-app'
            }
        }
    }
}