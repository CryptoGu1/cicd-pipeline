pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Application Build') {
            steps {
                sh 'chmod +x scripts/build.sh'
                sh './scripts/build.sh'
            }
        }

        stage('Tests') {
            steps {
                sh 'chmod +x scripts/test.sh'
                sh './scripts/test.sh'
            }
        }

        stage('Docker Image Build') {
            steps {
                // Замени 'my-name' на свою фамилию латиницей
                sh 'docker build -t my-app-image-my-name:${BUILD_NUMBER} .'
            }
        }
    }
}
