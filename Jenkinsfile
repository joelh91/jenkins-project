pipeline {
    agent any
    environment {
        SERVER_CREDS = credentials('server-c reds')
    }
    

    stages {

        
        stage('Setup') {
            steps {
                echo "my creds ${SERVER_CREDS}"
                echo "username ${SERVER_CREDS_USR}"
                echo "password ${SERVER_CREDS_PSW}"
                sh "pip install -r requirements.txt"
                  
            }
        }
        stage('Test') {
            steps {
                sh "pytest"
                echo "commit ${env.GIT_COMMIT}"
            }
        }
       
    }
}