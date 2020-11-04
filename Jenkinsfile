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
                sh 'mount /var/run/docker.sock /var/run/docker.sock'
                sh 'docker pull docker:19'
            }    
        }
        
    }
    
}
