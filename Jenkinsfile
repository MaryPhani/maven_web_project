pipeline {
    agent any
    stages {
        stage('build') {
        steps {
            echo "Maven_web_project"
        }
    }
    stage('Snyk Test') {
            steps {
                echo 'Snyk Testing...'
                snykSecurity (
                    projectName: 'snyk_security_tool', 
                    snykInstallation: 'snyk@latest', 
                    snykTokenId: 'organisation-snyk-api-token_1',
                    failOnIssues: false
                    
                )
            }
        }

  }
}
