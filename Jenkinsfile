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
    
    }

}