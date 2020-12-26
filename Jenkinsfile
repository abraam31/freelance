@Library('freelance') _

pipeline {
   agent any
   stages {
        stage('library groovy') {
			steps {
				script{ yaml("config.yml") }
				echo "Send on start: ${notificationOnStart}"
		}				
	}
}

   post {
		always {
			cleanWs ()
		}	
	}
}
