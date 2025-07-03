pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                    args '-u root:root'
                }
            }
            steps {
                sh '''
                    rm -rf node_modules package-lock.json ~/.npm
                    ls -la
                    node --version
                    npm --version
                    npm i
                    npm run build
                    ls -la
                '''
            }
        }
    }
}