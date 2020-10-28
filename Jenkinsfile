pipeline {
    agent {
       docker { image 'ruby:2.7.2' }
    }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {
        stage('Build') {
            steps {
                sh 'bundle update --bundler'
                sh 'bundle install'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}