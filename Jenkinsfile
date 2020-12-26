pipeline {
   agent any
   stages {
        stage('Read YAML file') {
			steps {
				script{ datas = readYaml (file: 'config.yml') }
				echo datas.build.buildCommand.toString()
				echo datas.build.projectFolder.toString()

		}
	}
}	

   post {
		always {
			cleanWs ()
		}	
	}
}


