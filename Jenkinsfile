pipeline {
  agent any
	stages {
		stage ('Checkout') {
			steps {
				git 'https://github.com/carlogilmar/Spring-Boot-Toy.git'
			}
		}
	}
	post {
		always {
			junit 'build/test-results/**/TEST-*.xml'
		}
	}
}
