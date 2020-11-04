pipeline {
    
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            agent {label "master"
                }
                
            }
            steps {
                sh 'pwd'
                sh 'ls -lrt'
                sh 'ruby --version'
            }    
        }
        
    }
    
}
