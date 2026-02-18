pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-FINAL', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://B210E5F11D66624C1F328583E21C18FB.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                 }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-FINAL', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://B210E5F11D66624C1F328583E21C18FB.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
