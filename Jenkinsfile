
pipeline {
    agent any

    environment {
        KUBECTL = 'D:\\DockerApp\\resources\\bin\\kubectl.exe'
        KUBECONFIG = 'C:\\Users\\POOVARASAN\\.kube\\config'
    }

    stages {
        stage('Deploy from GitHub') {
            steps {
                bat '"%KUBECTL%" apply -f deployment.yaml'
            }
        }

        stage('Verify Deployment') {
            steps {
                bat '"%KUBECTL%" rollout status deployment/auto-deploy-app --timeout=180s'
                bat '"%KUBECTL%" get deployment auto-deploy-app'
                bat '"%KUBECTL%" get pods -l app=auto-deploy-app'
            }
        }
    }
}
