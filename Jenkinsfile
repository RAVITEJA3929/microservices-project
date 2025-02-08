pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir ('src'){
                       withDockerRegistry(credentialsId: 'Dockerhub_credentials') {
                       sh " docker build -t pichashy/cartservice:latest . "
                         }
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Dockerhub_credentials') {
                     sh "docker push  pichashy/cartservice:latest  "
                    }
                }
            }
        }
    }
}
