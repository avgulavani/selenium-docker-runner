pipeline{
    agent any
    stages
    {
        stage("Pull latest images"){
            steps{
                sudo sh "docker pull avgulavani/selenium-docker"
            }
        }
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Test"){
            steps{
                sh "docker-compose up open-browser-module"
		        sh "docker-compose up simple-featurefile-test-module"
            }
        }

        } 
        post{
            always{
                archiveArtifacts artifacts:'output/**'
                sh "docker-compose down"
            }
    }
    }
