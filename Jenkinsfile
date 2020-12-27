@Library('freelance') _

pipeline {
   agent any
   stages {
        stage('library groovy') {
			steps {
				yaml("config.yml")	
		}				
	}
	
        stage('echoing vars') {
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


        stage('trying commands') {
			steps {
				
				sh """ 
					$env.pwdCommand
					echo "##############"					
					$env.listCommand
					echo "##########"
					cd $env.buildProjectFolder
					echo "##############"
					$env.pwdCommand
					echo "##############"					
					$env.listCommand
					"""
		}				
	}

        stage('test') {
			parallel {
				stage('Performance test'){
					steps {
						sh """
							cd $env.databaseProjectFolder
							$env.listCommand
						"""
					}
				}
				
				stage('Regression test'){
					steps {
						sh """
							cd $env.testFolder
							$env.listCommand
						"""
					}
				}
				
				stage('Integration test'){
					steps {
						sh """
							cd $env.buildProjectFolder
							$env.listCommand
						"""
					}
				}
			}
		}
	}

/*
        stage('build') {
			steps {
				sh """
					// Changing directory to project folder 
					cd $env.buildProjectFolder
					// executing the maven project command
					$env.buildCommand
				"""
		}				
	}

        stage('database') {
			steps {
				sh """
					// Changing directory to database folder 
					cd $env.databaseProjectFolder
					// executing the maven database command
					$env.databaseCommand
				"""
		}				
	}

        stage('deploy') {
			steps {
				sh """
					// Changing directory to deploy folder 
					cd $env.buildProjectFolder
					// executing the maven deploy command
					$env.deployCommand
				"""
		}				
	}

        stage('test') {
			parallel {
				stage('Performance test'){
					steps {
						sh """
							// Changing directory to project folder 
							cd $env.testFolder
							// executing the maven project command
							$env.performanceTestCommand
						"""
					}
				}
				
				stage('Regression test'){
					steps {
						sh """
							// Changing directory to project folder 
							cd $env.testFolder
							// executing the maven project command
							$env.regressionTestCommand
						"""
					}
				}
				
				stage('Integration test'){
					steps {
						sh """
							// Changing directory to project folder 
							cd $env.testFolder
							// executing the maven project command
							$env.integrationTestCommand
						"""
				}
			}
		}
	}

*/
   post {
		always {
			cleanWs ()
		}	
	}
}
