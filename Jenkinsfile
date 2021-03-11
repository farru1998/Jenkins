pipeline {
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
                  docker.withRegistry('https://registry.hub.docker.com/', 'docker-credential') {

        def customImage = docker.build("jenkin-test:${env.BUILD_ID}")

        /* Push the container to the custom Registry */
        customImage.push()
    }
            }
        }
    }
}
