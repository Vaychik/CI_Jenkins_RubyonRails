pipeline {
    agent {
       docker { image 'ruby:2.5' }
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {
        stage('Build') {
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
