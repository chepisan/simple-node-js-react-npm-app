pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3005:3000' 
        }
    }
    environment {
    CI = 'true' 
    }    
    stages {
        stage('Construir') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Prueba') { 
            steps {
                sh './jenkins/scripts/test.sh' 
            }
        }
    }
}
