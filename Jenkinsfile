pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build a Docker image with a simple "Hello World" program
                    docker.image('alpine:latest').inside {
                        sh 'echo "Hello, World!" > hello.txt'
                        sh 'cat hello.txt'
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Docker Hello World executed successfully!'
        }

        failure {
            echo 'Docker Hello World failed!'
        }
    }
}

