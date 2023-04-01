 pipeline {
     agent any
     stages {
      stage('checkout') {
       steps {
        git branch: 'main', credentialsId: '11c1e726-a404-43fd-9df0-58145ac8d502', url: 'https://github.com/akshay004/build_and_test_image'
      }
         stage('Building image') {
             steps {
                 script {
                     sh 'docker build -t ak .'
                 }
             }
         }
     }
 }
