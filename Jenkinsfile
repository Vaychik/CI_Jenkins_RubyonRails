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
        HOST_1 = 'ec2-18-217-246-9.us-east-2.compute.amazonaws.com'
    }
    
    stages {
        stage('Deploy Host 1') {
            steps {
                sh 'docker -H ${DOCKER_HOST} pull docker101tutorial'
                sh 'docker -H ${DOCKER_HOST} images'
                sh 'docker -H ${DOCKER_HOST} save -o $WORKSPACE/${IMAGE_FILE}.tar ${IMAGE_FILE}'
                sh 'ls -lrt $WORKSPACE'
                sh 'chmod 400 nomenclature.pem'
                sh 'scp -o StrictHostKeyChecking=no -i nomenclature.pem $WORKSPACE/${IMAGE_FILE}.tar ${USER}@${HOST_1}:/${IMAGE_PATH}'
                sh 'ssh -i nomenclature.pem ${USER}@${HOST_1} /scripts/deploy.sh'
                sh 'rm -f $WORKSPACES/${docker101tutorial}.tar'
            }    
        }
        
    }
    
}
