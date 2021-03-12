pipeline {
    environment{
        registry = "mfarhan1998/jenkins_test"
        registryCredentials = 'docker-credential'
        dockerImage = ''
    }
    agent any
    stages {
        stage('Build'){
            steps {
                sh 'ls' 
            }
        }
        stage('Building Image') {
            steps { 
                script{
                    dockerImage = docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }
        stage('Pushing Image'){
            steps{
                script{
                    docker.withRegistry('', registryCredential){
                        dockerImage.push()
                    }
                }     
              }    
            }
        }
    }
