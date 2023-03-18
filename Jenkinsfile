pipeline {
    environment {
    SECRET_SUDO_PASS=credentials("SECRET_SUDO_PASS")    
}
    agent {                          
            label 'ubuntu'
    }
    stages {
        stage('Download apache') {
            steps {
                echo 'Hello World'
                sh '''
		echo "$SECRET_SUDO_PASS" |  sudo -S apt install apache2
		echo "$SECRET_SUDO_PASS" |  sudo -S systemctl start apache2	
                '''
                echo 'World Hello'
            }
        }
    }
}
