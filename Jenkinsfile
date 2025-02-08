pipeline { 
    agent any

     stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker_credentials') {
                   sh " docker build -t pichashy/shippingservice:latest . "
                  }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker_credentials') {
                     sh "docker push  pichashy/shippingservice:latest  "
                    }
                }
            }
        }
    }
}
