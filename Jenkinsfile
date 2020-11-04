pipeline {
    
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    environment {
        DOCKER_HOST = 'localhost:2375'
    }
    
    stages {
        stage('Build') {
            agent {
                docker {image 'ruby --version'}
            }
            steps {
                sh 'ruby --version'
            }    
        }
        
    }
    
}
