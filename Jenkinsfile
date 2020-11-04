pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            tools {
                dockerTool 'Docker' 
            }
                
            steps {
                sh 'docker -v /var/run/docker.sock:/var/run/docker.sock pull docker/getting-started'
                sh 'ls -lrt'
                sh 'ruby --version'
            }    
        }
        
    }
    
}
