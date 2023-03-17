pipeline {
    agent {                          
            label 'ubuntu'
    }
    
    stages {
        stage('My-Pipeline') {
            steps {
                echo 'Hello World'
                sh '''
                ls -l
                '''
                echo 'World Hello'
            }
        }
    }
}

