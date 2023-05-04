#!groovy

node {
	   
	stage('Checkout'){

          checkout scm
       }

       stage('BuildArtifact'){

         // bat 'mvn install'
	       
	       sh 'mvn clean'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                   // sh 'mvn sonar:sonar'
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
