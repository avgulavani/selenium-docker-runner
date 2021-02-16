pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Test'){
            steps{
                sh "docker-compose up open-browser-module"
				sh "docker-compose up simple-featurefile-test-module"
            }

        }
		
        stage ("Stop Grid"){
            steps{
                sh "docker-compose down"
            }
        }    
        }
    }
