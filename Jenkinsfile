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
				sh './gradlew clean compileJava --no-daemon'
			}
		}
		stage('Unit-test'){
			steps {
				sh './gradlew test --no-daemon'
			}
		}
		stage('Integration-test'){
			steps {
				sh './gradlew integrationTest --no-daemon'
			}
		}
	}
	post {
		always {
			junit 'build/test-results/**/TEST-*.xml'
		}
	}
}
