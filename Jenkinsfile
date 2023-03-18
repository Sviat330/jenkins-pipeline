pipeline {
    environment {
    gpg_secret = credentials("gpg-secret")
    gpg_trust = credentials("gpg-ownertrust")
    gpg_passphrase = credentials("gpg-passphrase")
    SECRET_SUDO_PASS=credentials("SECRET_SUDO_PASS")    
}
    agent {                          
            label 'ubuntu'
    }
    
    stages {
	stage('Add gpg'){
	steps {
    sh """
        gpg --batch --import $gpg_secret
        gpg --import-ownertrust $gpg_trust
    """
	}
	}
	stage('Reveal sudo pass'){
	steps {
    sh """
        cd $WORKSPACE
        git secret reveal -p '$gpg_passphrase'
        git secret cat sudo_passwd.txt
    """
}
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

