pipeline {
	agent any
	
	stages {
		stage('maven validate code') {
			steps {
				echo 'validate'
				sh 'mvn validate'			
			}
		}
		stage('maven compile code') {
			steps {
				echo 'compile code'
				sh 'mvn compile'
			}
		}
	}
}
