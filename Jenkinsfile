pipeline {
    agent any
  
    stages {

        stage ('git') {
            steps {
                git branch: 'main', url: 'https://github.com/joelh91/jenkins-project'
            }
        }
        stage('Setup') {
            steps {
                sh "pip install -r requirements.txt"
            }
        }
        stage('Test') {
            steps {
                sh "pytest"
                sh "whoami"
            }
        }
        
    }
}