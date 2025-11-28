pipeline {
    agent any
   tools {
        nodejs 'nodejs-25-2-1'
    }
    stages{
        stage('Installing Dependencies'){
            steps{
                sh 'npm install --no-audit'
            }
        }

        stage('NPM Dependency Audit'){
            steps{
                sh '''
                npm audit --audit-level=critical
                echo $?
                '''
            }
        }
    
    }

}