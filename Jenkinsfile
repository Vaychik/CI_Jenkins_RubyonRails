pipeline {
    
    agent {label 'master'}

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    
    stages {
        stage('Build') {
            steps {
                sh 'docker -H tcp://0.0.0.0:2375 images'
                sh 'docker -H tcp://0.0.0.0:2375 save -o $WORKSPACE/docker101tutorial.tar docker101tutorial'
                sh 'ls -lrt $WORKSPACE'
                sh 'chmod 400 nomenclature.pem'
                sh 'scp -o StrictHostKeyChecking=no -i nomenclature.pem $WORKSPACE/docker101tutorial.tar ubuntu@ec2-18-217-246-9.us-east-2.compute.amazonaws.com:/images'
            }    
        }
        
    }
    
}
