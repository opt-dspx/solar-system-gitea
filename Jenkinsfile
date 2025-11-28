pipeline {
    agent any
   tools {
        nodejs 'nodejs-20.19.5'
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