pipeline {
    agent any

   stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                       withDockerRegistry(credentialsId: 'docker_credentials', toolName: 'docker') {
                         sh " docker build -t pichashy/frontent:latest . "
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_credentials', toolName: 'docker') {
                      sh "docker push  pichashy/frontent:latest  "
                    }
                }
            }
        }
    }
}
