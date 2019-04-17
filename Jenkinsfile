pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                node('FT4') {
                   sh 'npm install' 
             }
            }
        }
        stage('Test') {
            steps {
               node('FT4') {
                sh './jenkins/scripts/test.sh'
             }
            }
        }
    }
}
