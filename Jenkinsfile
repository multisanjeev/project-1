pipeline {
	agent any
	
	stages {
		stage('maven validate code') {
			steps {
				echo 'validate'
				sh 'mvn validate'			
			}
		}
	}
}
