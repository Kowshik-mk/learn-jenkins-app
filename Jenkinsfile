pipeline {
    agent any

    stages {
        stage('without-agent') {
            steps {
                echo 'Hello World'
                sh 'ls -la'
            }
        }
        stage('with-docker'){
            agent{
                docker{
                    image 'node:16.3.0-alpine'
                    reuseNode true
                }
            }
            steps{
                echo "docker container"
                sh 'ls -la'
            }
        }
    }
}
