pipeline {
    agent any

   stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'dockerhub_credentials') {
                   sh " docker build -t pichashy/adservice:latest . "
                  }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockerhub_credentials') {
                     sh "docker push  pichashy/adservice:latest  "
                    }
                }
            }
        }
    }
}
