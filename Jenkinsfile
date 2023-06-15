
    
pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
        stage('docker compose stop') {
          
            steps {
               bat 'docker-compose down'
            }
        }
           stage('docker compose start') {
          
            steps {
               bat 'docker-compose up -d'
            }
        }
        
         stage('push image') {
          
            steps {
               bat 'docker login -u hasee658 -p Nasha@786'
                bat 'docker push hasee658/compose_nginx_build:latest'
               // bat 'docker push hasee658/compose_nginx_build:latest'
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

               

