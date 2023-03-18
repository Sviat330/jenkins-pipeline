pipeline {
    agent {                          
            label 'ubuntu'
    }
    
    stages {
        stage('Download apache') {
            steps {
                echo 'Hello World'
                sh '''
                echo "$SUDO_PASS"| sudo -S apt update
		echo "$SUDO_PASS" |  sudo -S apt install apache2
                '''
                echo 'World Hello'
            }
        }
    }
}

