pipeline {
    agent any
    
    environment {
		DOCKERHUB_CREDENTIALS = credentials('fullaccess')
	}
    
    stages {
		stage('Build') {
			steps {
				sh 'docker build -t akshay:test-1 .'
			}
		}
		stage('Login') {
			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login ghcr.io -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
	    	stage('Tag') {
			steps {
				sh 'docker tag akshay:test-1 ghcr.io/akshay004/akshay:test-1 '
			}
		}
		stage('Push') {
			steps {
				sh 'docker push ghcr.io/akshay004/akshay:test-1 '
			}
		}
	}
	post {
		always {
			sh 'docker logout'
		}
	}
}
