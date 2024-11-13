pipeline {
    agent any
    

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
                echo "commit ${env.GIT_COMMIT}"
            }
        }
       
    }
}