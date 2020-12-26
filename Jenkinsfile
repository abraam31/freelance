@Library('freelance') _

def notificationOnStart

pipeline {
   agent any
   stages {
        stage('library groovy') {
			steps {
				yaml("config.yml")	
		}				
	}

        stage('vars') {
			steps {
				echo "#########################################################"
				echo "notification recipient is : ${env.notificationRecipient}"
				echo "Send on start: ${env.notificationOnStart}"
				echo "Send on failure: ${env.notificationOnFailure}"
				echo "Send on success: ${env.notificationOnSuccess}"
				
				echo "Build Project folder is: ${env.buildProjectFolder}"
				echo "Build command is: ${env.buildCommand}"
				echo "Database Project folder is: ${env.databaseProjectFolder}"
				echo "Database command is: ${env.databaseCommand}"
				echo "Deploy command is: ${env.deployCommand}"
				echo "Deploy Project folder is: ${env.buildProjectFolder}"
				echo "Test Project folder is: ${env.testFolder}"
				echo "performance test command is: ${env.performanceTestCommand}"
				echo "regression test command is: ${env.regressionTestCommand}"
				echo "integration test command is: ${env.integrationTestCommand}"		
		}				
	}
}
   post {
		always {
			cleanWs ()
		}	
	}
}
