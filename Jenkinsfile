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
		stage('code review') {
			steps {
				echo 'code review'
				sh 'mvn pmd:pmd'
			}
		}
		stage('maven test job') {
			steps {
				echo 'Test code job'
				sh 'mvn test'
			}
		}
	}
	
	post {
		always {
			junit 'target/surefire-reports/*.xml'
			pmd 'target/pmd.xml'
		}
	}
}
