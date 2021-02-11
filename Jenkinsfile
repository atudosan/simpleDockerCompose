pipeline {
    agent any
    stages {
        stage('Pull latest image') {
        	
            steps {
                
                bat "docker pull atudosan/simple-docker"
            }
        }
        stage('Start Grid') {
            steps {
                
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage('Run Test') {
            steps {
		
		bat "docker-compose up google facebook "
	    }
        }
    }
    post{
	always{
		bat "docker-compose down"
	}
    }
}