pipeline {
    agent any

   stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker-cred') {
                   sh " docker build -t raviteja3929/currencyservice:latest . "
                  }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                     sh "docker push raviteja3929/currencyservice:latest  "
                    }
                }
            }
        }
    }
}
