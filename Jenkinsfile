pipeline {
    
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            agent {
                docker {image 'docker:19'
                        args '-v /var/run/docker.sock:/var/run/docker.sock'
                }
            }
                
            steps {
                sh 'docker -H tcp://0.0.0.0:2375 images'
                sh 'docker -H tcp://0.0.0.0:2375 pull maven:latest'
            }    
        }
        
    }
    
}
