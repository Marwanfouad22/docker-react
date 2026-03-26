pipeline {
    agent any

    environment {
        DOCKER_BUILDKIT = '1'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t marwaan/docker-react -f Dockerfile.dev .'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh 'docker run --rm -e CI=true marwaan/docker-react npm run test'
                }
            }
        }
    }
}
