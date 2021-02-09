pipeline {
    agent any

    stages {
        stage('Image Scan') {
            steps {
                sh 'grype alpine:3.8'
            }
        }
    }

    post {
        always {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}
