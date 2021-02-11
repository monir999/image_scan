pipeline {
    agent any

    stages {
        stage('Image Scan') {
            steps {
                //sh 'My Name is Md'
                sh 'grype alpine:3.9.2'
            }
        }
    }

    post {
        always {
            dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        }
    }
}
