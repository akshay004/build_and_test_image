pipeline {
    agent any
    
	environment {
		DOCKERHUB_CREDENTIALS = credentials('fullaccess')
	}
   
    
    stages {
		
		stage('Login') {
			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login ghcr.io -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
		
	}

	post {
		always {
			sh 'docker logout'
		}
	}
}
