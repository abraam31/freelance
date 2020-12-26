@Library('freelance') _

def notificationOnStart

pipeline {
   agent any
   stages {
        stage('library groovy') {
			steps {
				yaml("config.yml")
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
