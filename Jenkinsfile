pipeline {
    agent any 
    stages {
       
            stage('Lint HTML') { 
            steps {
                tidy -q -e *.html 
            }
        }     
           stage('upload to AWS') { 
            steps {
                withAWS(credentials: 'aws-static', region: 'us-east-2') {
                    sh 'echo "hello KB">hello.txt'
                     s3Upload acl: 'Public', bucket: 'jenkinsbuket', file: 'index.html'
                }
            }
        } 
    }
 }
