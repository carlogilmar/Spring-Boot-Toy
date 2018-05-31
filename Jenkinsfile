pipeline {

  agent any

  tools {
    gradle "Gradle 2.10"
  }

	stages {
		stage ('Checkout') {
			steps {
				git 'https://github.com/carlogilmar/Spring-Boot-Toy.git'
        sh 'curl -X POST --data-urlencode "payload={\"channel\": \"#general\", \"username\": \"webhookbot\", \"text\": \"Jenkins says: Can you see me???.\", \"icon_emoji\": \":ghost:\"}" https://hooks.slack.com/services/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'
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

}
