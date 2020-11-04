pipeline {
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {
        stage('Build') {
            agent {
                docker { image 'docker:19' }
            }
            environment {
                  HOME="."
            }
            steps {
                sh 'docker pull docker/getting-started'
            }
        }
    }

    
}
