pipeline {
    agent any
    stages {
        
        stage('build'){
            steps{
                sh ' docker build -t akshay . '
                sh ' docker login ghcr.io -u $ghcr_user -p $CR_PAT '
                sh ' docker tag 3f8a00f137a0 ghcr.io/akshay004/akshay '
                sh ' docker push ghcr.io/akshay004/jenkins/akshay '
                sh ' docker logout ghcr.io '
            }
        }
    }
}
