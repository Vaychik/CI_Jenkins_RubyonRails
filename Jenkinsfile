pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'echo "export DOCKER_HOST=tcp://0.0.0.0:2375" >> ~/.bash_profile'
                sh 'docker images'
            
            }    
        }
        
    }
    
}
