pipeline {
    
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            agent {label "docker-agent"
                }
                
            steps {
                sh 'docker pull docker/getting-started'
                sh 'ls -lrt'
                sh 'ruby --version'
            }    
        }
        
    }
    
}
