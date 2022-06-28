pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build Networkings-DevOps-World Application'
            }
        }
        stage('Test') {
            steps {
                echo 'Test Networkings-DevOps-World Application'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy Networkings-DevOps-World Application'
            }
        }
    }
    post
    {

          always
          {
            emailext body: 'Kindly be informed the Pipeline Build is Successfully though some codes needs to be visited now.', subject: 'Pipeline Status Guys', to: 'sogsax@gmail.com'
          }

    }
}
