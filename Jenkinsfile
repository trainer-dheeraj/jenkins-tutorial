pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Build') {
            steps {
                echo "Application Build Successfully"
            }
        }
        stage('Test') {
            steps {
                bat 'npm test'
            }
        }
        stage('Start') {
            steps {
                bat 'npm start'
            }
        }
    }
}
