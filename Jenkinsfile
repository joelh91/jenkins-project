pipeline {
    agent any
    environment {
        DB_HOST = '172.168.12.1'
        USERNAME = 'user1'
        PASSWORD = 'password123'
    }

    stages {

        
        stage('Setup') {
            steps {
                sh "pip install -r requirements.txt"
                echo "the database ip is ${DB_HOST}"
            }
        }
        stage('Test') {
            steps {
                sh "pytest"
                echo "the database username is ${USERNAME} and the password is ${PASSWORD}"
            }
        }
       
    }
}