pipeline {
    environment {
        registry = "trainerdheerajsharma/demoapp"
        registryCredential = "docker"
        dockerImage = ''
    }
    agent any

    stages {
        stage('Install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                bat 'npm test'
            }
        }
        stage('Build') {
            steps {
                script {
                    dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    docker.withRegistry('', registryCredential) {
                    dockerImage.push()
                }
                }
            }
        }
    }
}
