pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                      withDockerRegistry(credentialsId: 'docker_credentials') {
                        sh " docker build -t pichashy/recommendationservice:latest . "
                   }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_credentials') {
                      sh "docker push  pichashy/recommendationservice:latest  "
                    }
                }
            }
        }
    }
}
