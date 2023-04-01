pipeline {
    agent any
    stages {
        
        stage('build'){
            steps{
                sh ' docker build -t akshay .'
                sh 'docker run -itd -p 8080:80 --name ubuntu-nginx ubuntu/nginx'
            }
        }
    }
}
