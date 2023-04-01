 pipeline {
     agent any
     tools {
         maven "MAVEN"
     }
     stages {
         stage('Building image') {
             steps {
                 script {
                     sh 'docker build -t ak .'
                 }
             }
         }
     }
 }
