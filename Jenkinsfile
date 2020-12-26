@Library('freelance') _

pipeline {
   agent any
   stages {
        stage('library groovy') {
			steps {
				yaml("config.yml")
				echo "#########################################################"
				echo "notification recipient is : ${notificationRecipient}"
				echo "Send on start: ${notificationOnStart}"
				echo "Send on failure: ${notificationOnFailure}"
				echo "Send on success: ${notificationOnSuccess}"
				
				echo "Build Project folder is: ${buildProjectFolder}"
				echo "Build command is: ${buildCommand}"
				echo "Database Project folder is: ${databaseProjectFolder}"
				echo "Database command is: ${databaseCommand}"
				echo "Deploy command is: ${deployCommand}"
				echo "Deploy Project folder is: ${buildProjectFolder}"
				echo "Test Project folder is: ${testFolder}"
				echo "performance test command is: ${performanceTestCommand}"
				echo "regression test command is: ${regressionTestCommand}"
				echo "integration test command is: ${integrationTestCommand}"
		}				
	}
}

   post {
		always {
			cleanWs ()
		}	
	}
}
