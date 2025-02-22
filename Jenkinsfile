pipeline {
    agent any

   stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker-cred') {
                   sh " docker build -t rohit630/paymentservice:latest . "
                  }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                     sh "docker push rohit630/paymentservice:latest  "
                    }
                }
            }
        }
    }
}
