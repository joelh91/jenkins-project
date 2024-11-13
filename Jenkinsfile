pipeline {
    agent any
    

    stages {

        
        stage('Setup') {
            steps {
                withCredentials([usernamePassword(credentialsID: 'server-c reds',
                usernameVariables: "myuser", passwordVariables: "mypassword")]) {
                    sh '''
                    echo ${myuser}
                    echo ${mypassword}
                    '''
                }
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