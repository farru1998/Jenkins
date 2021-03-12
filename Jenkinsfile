pipeline {
    def app
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
                app = docker.build("mfarhan/test")
                docker.withRegistry('https://registry.hub.docker.com', 'docker-credential') {                   
                    app.push("${env.BUILD_NUMBER}")            
                    app.push("latest")        
              }    
            }
        }
    }
}
