pipeline {
	agent { docker 'gradle:4.5-jdk8-alpine' }
	stages {
		stage ('Checkout') {
			steps {
				git 'here your repo url'
			}
		}
		stage('Build'){
			steps{
				sh 'gradle clean compileJava'
			}
		}
		stage('Unit-test'){
			steps {
				sh 'gradle test'
			}
		}
		stage('Integration-test'){
			steps {
				sh 'gradle integrationTest'
			}
		}
	}
	post {
		always {
			junit 'build/test-results/**/TEST-*.xml'
		}
	}
}
