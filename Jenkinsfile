pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "image-name"
        DOCKER_TAG = "latest"
        DOCKER_REGISTRY_URL = "https://your-docker-registry-url"
        DOCKER_REGISTRY_CREDENTIALS_ID = "your-docker-registry-credentials-id"
        TRIVY_SEVERITY = "HIGH,CRITICAL"
        TRIVY_TIMEOUT = "10m"
    }

    stages {
        stage('Trivy Scan') {
            steps {
                script {
                    // Run Trivy scan with the specified command
                    sh "trivy image -o trivy-report.txt image-name"
                    
                    // Archive the report
                    archiveArtifacts artifacts: 'trivy-report.txt', allowEmptyArchive: true
                }
            }
        }

        stage('Deploy Application') {
            steps {
                echo "Deploying application..."
                // Add your deployment steps here
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}

