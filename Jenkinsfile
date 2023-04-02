pipeline {
    agent any
    stages {
        
        stage('build'){
            steps{
                sh ' docker build -t akshay . '
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh ' docker tag 3f8a00f137a0 ghcr.io/akshay004/akshay '
                sh ' docker push ghcr.io/akshay004/jenkins/akshay '
                sh ' docker logout ghcr.io '
            }
        }
    }
}
