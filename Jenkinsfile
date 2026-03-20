pipeline {
    agent{
        docker{
            image 'node:18.3.0-alpine'
            reuseNode true
        }
    }
    stages {
        stage('Build'){
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
        stage('Test'){
            steps{
                echo "testing the workspace"
                sh '''
                ls -la
                test -f build/index.html
                npm test
                '''
            }
        }

        
}
    post{
        always{
            junit 'test-results/junit.xml'
        }
    }
}
