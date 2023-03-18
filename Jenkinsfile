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
	stage('Checking log file for errors') {
	    steps {
		sh '''#/bin/bash
echo $SHELL		
echo "$SECRET_SUDO_PASS" | sudo -S cat /var/log/apache2/access.log | grep -E '\" (4[0-9]{2}|5[0-9]{2})'

		'''
}
    }
}
}
