pipeline {
    agent any  // Use any available agent

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/jishnump/Jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'make'
            }
        }

        stage('Test') {
            steps {
                sh './main'
            }
        }

        stage('Clean Up') {
            steps {
                sh 'make clean'
            }
        }
    }
}
