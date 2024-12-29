pipeline {
    agent any

    stages {
        stage('build-docker-image') {
            steps {
                getGitRepository()
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
def getGitRepository(){
    echo "Getting Git repository via script"
    git branch: 'main', url: 'https://github.com/tomsbozis/api-tests-final'
}

def buildDockerImage(){
    echo "Start building Docker image without cache"
    sh "docker build --no-cache -t tomsbozis/api-tests-final:latest ."
    echo "Start pushing Docker image"
    sh "docker push tomsbozis/api-tests-final"
}