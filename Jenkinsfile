pipeline {
    agent any

     triggers {
        githubPush()
        // problems as webhook can't be placed on localhost Jenkins etc..
    }

    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image"
                echo "Check if Docker is accessible via jenkins"
                sh 'docker --version'

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
    // sh "docker push tomsbozis /api-tests-final"
}