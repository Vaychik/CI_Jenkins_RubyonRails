pipeline {
    agent {
                docker { image 'ruby:2.6.2' }
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {
        stage('Build') {
            agent {
                docker { image 'docker:19' }
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
