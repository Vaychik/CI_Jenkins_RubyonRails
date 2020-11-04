pipeline {
    agent {
        docker {image 'ruby:2.6.2'}
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    environment {
        DOCKER_HOST = 'localhost:2375'
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'ruby --version'
            }    
        }
        
    }
    
}
