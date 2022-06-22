pipeline {
    agent any 
    environment {
    DOCKERHUB_CREDENTIALS = credentials('mayor1docker')
    }
    stages { 
        stage('SCM Checkout') {
            steps{
            git 'https://github.com/Mayokun-DevOps/Nodejs-Project.git'
            }
        }

        stage('Build docker image') {
            steps {  
                sh 'docker build -t mayor1docker/git-jenkins:$BUILD_NUMBER .'
            }
        }
        stage('login to dockerhub') {
            steps{
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('push image') {
            steps{
                sh 'docker push mayor1docker/git-jenkins:$BUILD_NUMBER'
            }
        }
}
post {
        always {
            sh 'docker logout'
        }
    }
}

