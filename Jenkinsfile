pipeline {
    agent any
    

    stages {

        
        stage('Setup') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'server-c reds',
                usernameVariable: "myuser", passwordVariable: "mypassword")]) {
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