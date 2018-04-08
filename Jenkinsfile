pipeline {
  agent any
	stages {
		stage ('Checkout') {
			steps {
				git 'https://github.com/carlogilmar/Spring-Boot-Toy.git'
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
