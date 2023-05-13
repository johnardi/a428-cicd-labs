node {
    checkout scm
    
    def customImage = docker.image('node:16-buster-slim').withRun(' -p 3306:3306')

    customImage.inside {
        stage('Build') { 
            sh 'npm install' 
        }
        stage('Test') { 
                sh './jenkins/scripts/test.sh' 
        }
    }
}