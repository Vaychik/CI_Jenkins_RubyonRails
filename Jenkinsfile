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
                sh 'bundle lock --add-platform x86-mingw32 x86-mswin32 x64-mingw32 java'
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