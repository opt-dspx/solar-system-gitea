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
        stage('dependency Scanning'){
           parallel{
              stage('NPM Dependency Audit'){
                steps{
                    sh '''
                    npm audit --audit-level=critical
                    echo $?
                    '''
                    }
                } 
            //   stage('OWASP Dependency Check'){
            //     steps{
            //      dependencyCheck additionalArguments: '''
            //      --scan \'./\'
            //      --out \'./\'
            //      --format \'ALL\'
            //      --prettyPrint''', odcInstallation: 'OWASP-DepCheck-10'
            //      dependencyCheckPublisher failedTotalCritical: 1, pattern: 'dependency-check-report.xml', skipNoReportFiles: true
            //      publishHTML([allowMissing: true, alwaysLinkToLastBuild: true, icon: '', keepAll: true, reportDir: './', reportFiles: 'dependency-check-jenkins.html', reportName: 'Dependency Check HTML Report', reportTitles: '', useWrapperFileDirectly: true])
            //     }
            //   }
            }
      
        
        }
        stage('Build Docker Image'){
            steps{
                sh 'docker build -t opt-dspx/solar-system-gitea:$GIT_COMIT:'
            }
        }
    
    }


}