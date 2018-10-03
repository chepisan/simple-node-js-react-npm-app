pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3005:3000' 
        }
    }
    stages {
        stage('Construir') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
