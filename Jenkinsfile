#!groovy

node {
	   
	stage('Checkout'){

          checkout scm
       }

       stage('BuildArtifact'){

         // bat 'mvn install'
	       
	       sh 'mvn clean install'
       }
	   
                
      stage('Snyk Test') {
            stage {
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
