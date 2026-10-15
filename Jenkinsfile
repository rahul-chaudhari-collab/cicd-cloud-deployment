
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-website .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                    docker rm -f cicd-container || true
                    docker run -d \
                        --name cicd-container \
                        -p 8081:80 \
                        --restart unless-stopped \
                        cicd-website
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'docker ps --filter name=cicd-container'
                sh 'curl -f http://localhost:8081'
            }
        }
    }

    post {
        success {
            echo 'CI/CD pipeline completed successfully!'
        }
        failure {
            echo 'CI/CD pipeline failed. Check the console output.'
        }
    }
}

