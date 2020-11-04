pipeline {
    
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            agent {
                docker {image 'ruby:2.6.2'
                alwaysPull true
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
