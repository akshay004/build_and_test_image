pipeline {
    agent { dockerfile true }
    stages {
        
        stage('build'){
            steps{
                sh 'docker build -t ak .
            }
        }
    }
}
