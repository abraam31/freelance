pipeline {
   agent any
   stages {
        stage('Read YAML file') {
			steps {
				script{ datas = readYaml (file: 'config.yml') }
				buildCommand = datas.build.buildCommand.toString()
				projectFolder = datas.build.projectFolder.toString()
				echo $projectFolder
				echo buildCommand

		}
	}
}	

   post {
		always {
			cleanWs ()
		}	
	}
}


