pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'docker -H tcp://0.0.0.0:2375 images'
                sh 'docker -H tcp://0.0.0.0:2375 save -o $WORKSPACE/docker101tutorial.tar docker101tutorial'
                sh 'ls -lrt $WORKSPACE'
            }    
        }
        
    }
    
}
