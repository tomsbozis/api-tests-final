pipeline {
    agent any
    // testing trigger
    // second test
     triggers {
        githubPush()
    }

    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image"
                buildDockerImage()
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