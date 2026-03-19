pipeline {
    agent any

    stages {
        stage('install-dependencies and build'){
            agent{
                docker{
                    image 'node:18.3.0-alpine'
                    reuseNode true
                }
            }
            steps{
                echo "install dependencies"
                sh '''
                  ls -la
                  npm ci
                  ls -la
                  echo 'building app'
                  npm run build
                  ls -la
                  '''
            }
        }
        
}
}
