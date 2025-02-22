pipeline { 
    agent any

     stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'Dockerhub_credentials') {
                   sh " docker build -t rohit630/shippingservice:latest . "
                  }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'Dockerhub_credentials') {
                     sh "docker push  rohit630/shippingservice:latest  "
                    }
                }
            }
        }
    }
}
