pipeline {
    agent any
    
    environment {
		DOCKERHUB_CREDENTIALS = credentials('fullaccess')
	}
    
    stages {
		stage('Build') {
			steps {
				sh 'docker build -t akshay:latest .'
			}
		}
		stage('Login') {
			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login ghcr.io -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
	    	stage('Tag') {
			steps {
				sh 'docker tag akshay:latest ghcr.io/akshay004/akshay:latest '
			}
		}
		stage('Push') {
			steps {
				sh 'docker push ghcr.io/akshay004/akshay:latest '
			}
		}
	}
	post {
		always {
			sh 'docker logout'
		}
	}
}
