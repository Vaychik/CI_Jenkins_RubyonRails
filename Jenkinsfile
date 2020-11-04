pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    environment {
        IMAGE_PATH = '/images'
        IMAGE_FILE = 'docker101tutorial'
        DOCKER_HOST = 'tcp://0.0.0.0:2375'
        HOST_1 = 'ec2-18-217-246-9.us-east-2.compute.amazonaws.com'
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'docker -H ${DOCKER_HOST} images'
                sh 'docker -H ${DOCKER_HOST} save -o $WORKSPACE/${IMAGE_FILE}.tar ${IMAGE_FILE}'
                sh 'ls -lrt $WORKSPACE'
                sh 'chmod 400 nomenclature.pem'
                sh 'scp -o StrictHostKeyChecking=no -i nomenclature.pem $WORKSPACE/${IMAGE_FILE}.tar ubuntu@${HOST_1}:/${IMAGE_PATH}'
                sh 'ssh -i nomenclature.pem ubuntu@{HOST_1} /scripts/deploy.sh'
            }    
        }
        
    }
    
}
