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
                sh 'gem install bundler:1.16.3'
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