pipeline {
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {
        stage('Build') {
            agent {
                docker { image 'ruby:2.6.2' }
            }
            steps {
                sh 'docker pull docker/getting-started'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
