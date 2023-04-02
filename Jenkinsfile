pipeline {
    agent any
    
    environment {
		DOCKERHUB_CREDENTIALS=credentials('git-hub')
	}
    
    stages {
        
        stage('build'){
            steps{
                sh ' docker build -t akshay . '
            }
        }
        stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
    }
}
