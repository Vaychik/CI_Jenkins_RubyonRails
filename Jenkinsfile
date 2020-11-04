pipeline {
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            agent {docker 'docker:19'}
            steps {
                cmd 'docker'
            }    
        }
        
    }
    
}
