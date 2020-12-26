@Library('freelance') _

pipeline {
   agent any
   stages {
        stage('library groovy') {
			steps {
				yaml("config.yml")
		}				
	}
}

   post {
		always {
			cleanWs ()
		}	
	}
}
