pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'echo "export DOCKER_HOST=localhost:2375" >> ~/.bash_profile'
                sh 'docker images'
            
            }    
        }
        
    }
    
}
