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
		stage('Push') {
			steps {
				
				sh ' docker tag `docker images --format="{{.Repository}} {{.ID}}" |  grep "^akshay" |  cut -d' ' -f2 |  xargs` ghcr.io/akshay004/akshay:latest ' 
				sh 'docker push ghcr.io/akshay004/jenkins/akshay:latest '
			}
		}
	}
	post {
		always {
			sh 'docker logout'
		}
	}
}
