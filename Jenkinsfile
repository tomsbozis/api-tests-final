pipeline {
    agent any
    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image"
            }
        }
        stage('deploy-dev') {
            steps {
                echo "Deployment triggered on DEV env"
            }
        }
        stage('test-dev') {
            steps {
                echo "API test triggered on DEV env"
            }
        }
    }
}