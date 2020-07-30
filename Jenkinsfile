pipeline {
    agent any 
    stages {
       
           stage('Lint HTML') {
            steps {
                withAWS(credentials: 'aws-credentials', region: 'us-east-1') {
                    sh 'echo "hello KB">hello.txt'
                    s3Upload acl: 'Private', bucket: 'kb-bucket', file: 'hello.txt'
                }
            }
           }     
           stage('upload to AWS') { 
            steps {
                withAWS(credentials: 'aws-static', region: 'us-east-2') {
                    sh 'echo "hello KB">hello.txt'
      
                }
            }
        } 
    }
 }
