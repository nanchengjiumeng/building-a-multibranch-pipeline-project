// fasefaef
pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3003:3003' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'npm i' 
            }
        }
        stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver-for-development.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }
    }
}