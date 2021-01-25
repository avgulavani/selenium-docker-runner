pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hum chrome firefox"
            }
        }
        stage("Run Test"){
            steps{
                sh "docker-compose up open-browser-module"
            }
        }
        stage ("Stop Grid"){
            steps{
                sh "docker-compose down"
            }
        }    
        }
    }
