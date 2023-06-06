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
              sh 'docker build -t ubun.im:latest .'
            }
        }
         stage('Tag Image') {
           
            steps {
               sh 'docker tag ubun:latest hasee658/ubun.im:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               sh 'docker login -u hasee658 -p hasee658#'
                sh 'docker push ubun.im:latest'
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

               

