pipeline {
    agent any

    stages {
        stage('Image Scan') {
            steps {
                sh 'echo monir'
                sh 'grype alpine:3.9.2'
            }
        }
    }

    post {
        always {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
            dependencyCheck additionalArguments: '', odcInstallation: 'OWSAP-Dependency-Check'
        }
    }
}
