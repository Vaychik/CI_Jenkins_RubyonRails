pipeline {
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            agent {docker 'docker:19'}
            steps {
                docker.image('ubuntu1804').withRun('-w /$PWD -v /$PWD:/$PWD') {c ->
                docker.image('ubuntu1804').inside{
               /*  Do something here inside container  */
               sh "ls"
               }
               }
            }
        }
        
    }
    
}
