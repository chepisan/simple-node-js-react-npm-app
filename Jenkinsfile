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
        stage('Entrega') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
         
    }
}
