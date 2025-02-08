pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir ('src'){
                       withDockerRegistry(credentialsId: 'docker_credentials') {
                         sh " docker build -t pichashy/paymentservice:latest . "
                         }
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_credentials') {
                      sh "docker push  pichashy/paymentservice:latest  "
                    }
                }
            }
        }
    }
}
