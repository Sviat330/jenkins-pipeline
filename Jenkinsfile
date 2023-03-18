pipeline {
    environment {
    SECRET_SUDO_PASS=credentials("SECRET_SUDO_PASS")    
}
    agent {                          
            label 'ubuntu'
    }
    
        stage('Download apache') {
            steps {
                echo 'Hello World'
                sh '''
		sudo whoami
                echo "$SECRET_SUDO_PASS" | sudo -S apt update
		echo "$SECRET_SUDO_PASS" |  sudo -S apt install apache2
                '''
                echo 'World Hello'
            }
        }
    }
}

