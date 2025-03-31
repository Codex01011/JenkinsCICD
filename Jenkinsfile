pipeline {
    
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:22.14.0-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    # list all files
                    ls -la
                    node --version
                    npm --version
                    # npm install
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }

        // stage('Test') {
        //     agent {
        //         docker {
        //             image 'node:22-alpine'
        //             reuseNode true
        //         }
        //     }

        //     steps {
        //         sh '''
        //             test -f build/index.html
        //             npm test
        //         '''
        //     }
        // }
        // stage('Build My Docker Image'){
        //     agent {
        //         docker {
        //             image 'amazon/aws-cli'
        //             reuseNode true
        //             args '-u root -v /var/run/docker.sock:/var/run/docker.sock --entrypoint=""'
        //         }
        //     }
        //     steps{
        //         sh '''
        //             amazon-linux-extras install docker
        //             docker build -t my-docker-image .
        //         '''
        //     }
        }
       
    }
}