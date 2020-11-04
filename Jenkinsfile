pipeline {
    agent none

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stage('BuildInside') {
         docker.image('ubuntu1804').withRun('-w /$PWD -v /$PWD:/$PWD') {c ->
            docker.image('ubuntu1804').inside{
               /*  Do something here inside container  */
               sh "ls"
            }
        }
  }

    
}
