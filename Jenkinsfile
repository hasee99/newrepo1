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
              bat 'docker build -t ubun1 .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'docker tag ubun1:latest hasee658/ubun1:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hasee658 -p Nasha@786#'
                bat 'docker push hasee658/ubun1:latest' 
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

               

