
pipeline {
	agent any
	}	
	
	environment {
		EXECUTE = 'true'
	}	
		
	
		stages {
			
			stage('First') {
				steps {
					sh '''
						echo "Step One"
					'''
					script { env.EXECUTE ="true"}
					   }
				}
			}


			stage('Second') {
				when { environment name: 'EXECUTION', value: 'true'}	
				}
				steps {
					sh '''
						echo "Step Two"
						echo "Updating Second Stage"
					'''
				           }
				}
			} 

			stage('Third') {
				when { not { environment name: 'EXCUTION', calue: 'true'}}
				steps {
					sh '''
						echo "Step Three"
					'''
				}
			}
		}
}

