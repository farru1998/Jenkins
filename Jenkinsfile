pipeline {
    environment {
    registry = "mfarhan1998/jenkins_latest"
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
