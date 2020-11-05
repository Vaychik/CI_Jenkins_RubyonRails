pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    environment {
        IMAGE_PATH = '/images'
        IMAGE_FILE = 'docker101tutorial'
        DOCKER_HOST = 'tcp://0.0.0.0:2375'
        USER = 'ubuntu'
        HOST_IP_1 = '3.139.78.93'
        CRED_FILE = credentials('nomenclature')
    }
    
    stages {
        stage('Deploy Host 1') {
            steps {
                sh 'docker -H ${DOCKER_HOST} pull docker/getting-started'
                sh 'docker tag docker/getting-started:latest ${IMAGE_FILE}:latest'
                sh 'docker -H ${DOCKER_HOST} images'
                sh 'docker -H ${DOCKER_HOST} save -o $WORKSPACE/${IMAGE_FILE}.tar ${IMAGE_FILE}'
                sh 'ls -lrt $WORKSPACE'
                // sh 'chmod 400 nomenclature.pem'
                sh 'scp -o StrictHostKeyChecking=no -i ${CRED_FILE} $WORKSPACE/${IMAGE_FILE}.tar ${USER}@${HOST_IP_1}:/${IMAGE_PATH}'
                sh 'ssh -i ${CRED_FILE} ${USER}@${HOST_IP_1} /scripts/deploy.sh'
            }    
        }
        
    }
    
    post { 
        always {
            sh 'rm -f $WORKSPACE/${IMAGE_FILE}.tar'
        }
    }
    
}
