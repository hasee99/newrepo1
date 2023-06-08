pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
         stage('Build Image') {
            steps {
              bat 'docker build -t ubuntu1 .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'docker tag ubuntu1:latest hasee99/ubuntu1:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hasee658 -p Nasha@786#'
                bat 'docker push hasee658/ubuntu:latest' 
            }
        }
    }
    post { 
        aborted { 
            echo 'ABORTED' 
        }
         success { 
            echo 'SUCCESS'
        }
         failure { 
            echo 'FAILURE'
        }
        changed { 
            echo 'FAILURE'
        }
    }
    
}

               

