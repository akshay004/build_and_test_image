pipeline {
    agent any
    
   
    
    stages {

		stage('Build') {

			steps {
				sh 'docker build -t akshay:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo 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 | docker login ghcr.io -u akshay004 --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push ghcr.io/akshay004/jenkins/akshay'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}
}
