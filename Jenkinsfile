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
              bat 'docker build -t ubun.im:latest .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'docker tag ubun:latest hasee658/ubun.im:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hasee658 -p hasee658#' 
                bat 'docker push ubun.im:latest'
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

               

