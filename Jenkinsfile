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
              bat 'docker build -t docimage:latest .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'docker tag docimage:latest hasee658/docimage:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hasee658 -p hasee658#' 
                bat 'docker push docimage:latest'
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

               

