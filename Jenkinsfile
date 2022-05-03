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
		stage('Matrix check through cobertura') {
			steps {
				sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'
			}
		}
	}
	
	post {
		always {
			junit 'target/surefire-reports/*.xml'
		}
	}
}
