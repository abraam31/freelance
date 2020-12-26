pipeline {
   agent any
   stages {
        stage('Read YAML file') {
			steps {
				script{
					//parsing the yaml file 
					datas = readYaml (file: 'config.yml') 
					
					// notifications vars 
					notificationRecipient = datas.notifications.email.recipients.toString()
					notificationOnStart = datas.notifications.email.on_start.toString()
					notificationOnFailure = datas.notifications.email.on_failure.toString()
					notificationOnSuccess = datas.notifications.email.on_success.toString()


					
					
					// build vars 
					buildCommand = datas.build.buildCommand.toString()
					buildProjectFolder = datas.build.projectFolder.toString()
					
					// Database vars 
					databaseCommand = datas.database.databaseCommand.toString()
					databaseProjectFolder = datas.database.databaseFolder.toString()

					// deploy vars 
					deployCommand = datas.deploy.deployCommand.toString()


					}
					
				echo "notification recipient is : ${notificationRecipient}"
				echo "Send on start: ${notificationOnStart}"
				echo "Send on failure: ${notificationOnFailure}"
				echo "Send on success: ${notificationOnSuccess}"
				
				echo "Build Project folder is: ${buildProjectFolder}"
				echo "Build command is: ${buildCommand}"
				echo "Database Project folder is: ${databaseProjectFolder}"
				echo "Database command is: ${databaseCommand}"
				echo "Deploy command is: ${deployCommand}"
				
		}
	}
}	

   post {
		always {
			cleanWs ()
		}	
	}
}


