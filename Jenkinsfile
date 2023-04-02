pipeline {
    agent any
    
    environment {
		DOCKERHUB_CREDENTIALS = credentials('fullaccess')
	}
    
    stages {
        stage('login'){
            steps{
		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
    }
}
