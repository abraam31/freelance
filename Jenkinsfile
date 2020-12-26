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

					// test vars 
					testFolder = datas.test[0].testFolder.toString()

					performanceTestCommand = datas.test[0].testCommand.toString()
					regressionTestCommand = datas.test[1].testCommand.toString()
					integrationTestCommand = datas.test[2].testCommand.toString()

					// build vars 
					buildCommand = datas.build.buildCommand.toString()
					buildProjectFolder = datas.build.projectFolder.toString()
					
					// Database vars 
					databaseCommand = datas.database.databaseCommand.toString()
					databaseProjectFolder = datas.database.databaseFolder.toString()

					// deploy vars 
					deployProjectFolder = datas.build.projectFolder.toString()
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


