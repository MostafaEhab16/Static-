pipeline {
    agent any 
    stages {
       
           stage('upload to AWS') { 
            steps {
                withAWS(credentials: 'aws-static', region: 'us-east-2') {
                    sh 'echo "hello KB">hello.txt'
      
                }
            }
        } 
    }
 }
