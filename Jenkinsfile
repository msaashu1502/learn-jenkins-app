pipeline {
    agent any

    stages {
        stage('Build') {
            // Here we are defining an agent 
            agent {
                // The agent is docker
                docker {
                    // In the docker configuration we are specifying an image and the image is node:18-alpine
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}