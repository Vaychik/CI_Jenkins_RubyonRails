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
                docker {image 'docker:19'}
            }
            steps {
                sh 'docker version'
            }    
        }
        
    }
    
}
