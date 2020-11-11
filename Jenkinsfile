pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
            HOME = '.'
    }
    stages {
        stage('Initial') {
            steps {
                echo "Testing Initial \n\n\n\n ======================= ${env.Environment}."
                echo 'Testing Initial \n\n\n\n =======================.' 
            }
        }
        stage('Install') {
            steps {
                sh 'npm install' 
            }
        }
        stage('Test') { 
            steps {
                sh 'npm run test' 
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build' 
            }
        }
        stage('Deliver') { 
            steps {
                sh 'npm publish --dry-run' 
            }
        }
    }
}
