pipeline {
    agent any  // Use any available agent

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/jishnump/Jenkins.git'
            }
        }

        stage('Static Code Analysis') {
            steps {
                sh 'cppcheck --enable=all --xml --xml-version=2 . 2> cppcheck-report.xml || true'
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
