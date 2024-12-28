pipeline {
    agent any

    environment {
        PATH = "/Applications/Docker.app/Contents/Resources/bin:$PATH"
    }

    stages {
        stage('build-docker-image') {
            steps {
                echo "Building docker image"
                echo "Check current PATH"
                sh 'echo $PATH'  // Add this line to confirm the PATH is correct
                echo "Check Docker version"
                sh 'docker --version'
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
    echo "Start building Docker image"
    sh "docker build -t tomsbozis/api-tests-final:latest ."
    echo "It went well and it is built"
    // sh "docker push tomsbozis/api-tests-final"
}