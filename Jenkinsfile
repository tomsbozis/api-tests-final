pipeline {
    agent any

    environment {
        PATH = "/Applications/Docker.app/Contents/Resources/bin:$PATH"
    }

    triggers {
        githubPush()
    }

    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image"
                echo "Check if Docker is accessible via jenkins"
                sh 'which docker'
                sh 'whereis docker'
                sh 'docker --version'  // Check Docker version inside Jenkins

                // Commented out buildDockerImage to just check Docker availability
                // buildDockerImage()
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

def buildDockerImage(){
    sh "docker build -t tomsbozis/api-tests-final:latest ."
    echo "Pushing image to docker registry.."
    // sh "docker push tomsbozis/api-tests-final"
}