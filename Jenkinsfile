pipeline {
    
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            tools {
                dockerTool 'Docker' 
            }
                
            steps {
                sh 'docker pull -v /var/run/docker.sock:/var/run/docker.sock docker/getting-started'
                sh 'ls -lrt'
                sh 'ruby --version'
            }    
        }
        
    }
    
}
