pipeline {
   agent any
   stages {
        stage('Read YAML file') {
			steps {
				script{ datas = readYaml (file: 'config.yml') }
				echo datas.ear_file.deploy.toString()
		}
	}
}	

   post {
		always {
			cleanWs ()
		}	
	}
}


