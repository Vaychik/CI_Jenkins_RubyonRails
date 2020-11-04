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
                sh 'docker pull docker/getting-started'
            }    
        }
        
    }
    
}
