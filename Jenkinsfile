pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'happy_cluster', contextName: '', credentialsId: '', namespace: 'default', restrictKubeConfigAccess: false, serverUrl: 'https://1747171A70711F5D0440C29DB9CEEEA2.gr7.ap-south-1.eks.amazonaws.com') {
                    sh "kubectl apply -f deployment-service.yml"
                    
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'happy_cluster', contextName: '', credentialsId: '', namespace: 'default', restrictKubeConfigAccess: false, serverUrl: 'https://1747171A70711F5D0440C29DB9CEEEA2.gr7.ap-south-1.eks.amazonaws.com') {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}
