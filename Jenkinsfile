pipeline {
   agent any
   stages {
        stage('Read YAML file') {
			steps {
				script{
					//parsing the yaml file 
					datas = readYaml (file: 'config.yml') 
					
					// build vars 
					buildCommand = datas.build.buildCommand.toString()
					buildProjectFolder = datas.build.projectFolder.toString()
					
					// Database vars 
					databaseCommand = datas.database.databaseCommand.toString()
					databaseProjectFolder = datas.database.databaseFolder.toString()

					// deploy vars 
					deployCommand = datas.deploy.deployCommand.toString()


					}
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


