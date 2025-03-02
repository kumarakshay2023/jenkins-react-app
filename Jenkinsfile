pipeline {
    agent any

    stages {
        stage('build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                 ls -a 
                 node --version
                 npm --version
                 npm ci
                 npm run build
                 ls -la
                 '''
            }
        }
        stage("test") {
               agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
  sh '''
             echo "Test stage"
             npm test
            

           '''
            }
         
        }
    }
}
