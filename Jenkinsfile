pipeline {
	agent any 

	environment {
		GO_VERSION = '1.18' // specify the version of Go you want to use 
		}

	stages {
		stage('Checkout') {
			steps {
				git url: 'https://github.com/helloabhii/jenkins-play.git', branch: 'main'
			}
		}

		stage('Set up Go environment') {
			steps {
				git url: 'https://github.com/helloabhii/jenkins-play.git', branch: 'main'
			}
		}

		stage('Build') {
			steps {
				sh 'go build -o myapp main.go'
			}
		}

		stage('Test') {
			steps {
				sh 'go test ./...'
			}
		}

		stage('Archive') {
			steps {
				archiveArtifacts artifacts: 'myapp', allowEmptyArchive: true 
			}
		}	
	}

	post {
		always {
			cleanWs()
		}
	}
}
