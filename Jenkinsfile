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
				sh 'gradle clean compileJava --no-daemon'
			}
		}
		stage('Unit-test'){
			steps {
				sh 'gradle test --no-daemon'
			}
		}
		stage('Integration-test'){
			steps {
				sh 'gradle integrationTest --no-daemon'
			}
		}
	}
	post {
		always {
			junit 'build/test-results/**/TEST-*.xml'
		}
	}
}
