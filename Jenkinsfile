pipeline {
    agent any
   tools {
        nodejs 'nodejs-25-2-1'
    }
    stages{
        stage('VM Node Version'){
            steps{
                sh '''
                node -v
                npm -v
                '''
            }
        }
    
    }

}