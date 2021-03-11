pipeline {
    environment {
    registry = "https://hub.docker.com"
    registryCredential = 'docker-credential'
    }
    agent any
    stages {
        stage('myStage'){
            steps {
                sh 'ls -la' 
            }
        }
        stage('Build') {
            steps { 
                sh 'ls' 
            }
        }
        stage('Image'){
            steps{
                script {
                   docker.build registry + ":$BUILD_NUMBER"
               }
            }
        }
    }
}
