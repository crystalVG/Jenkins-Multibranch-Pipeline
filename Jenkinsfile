pipeline {	
	agent any
		
	environment {
		EXECUTE = 'true'
	}	
		
	
	stages {
			
	stage('First') {
			steps {
				echo "${execute}
				sh '''
					echo "Step One"
				'''
			       }
			}
		}


		zstage('Second') {
			when { environment name: 'EXECUTE', value: 'true'}	
			steps {
				sh '''
					echo "Step Two"
					echo "Updating Second Stage"
				'''
	                	}
		} 

		stage('Third') {
				when { not { environment name: 'EXECUTE', value: 'true'}}
				steps {
					sh '''
						echo "Step Three"
					'''
				}
			}

}
