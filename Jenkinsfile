pipeline {
  agent any
  tools { 
        maven 'maven_3.5.2'  
    }
   stages{
    stage('SonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=arorakamal -Dsonar.organization=arorakamal -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=ce5056eb245049dd528994206b023e6cec243cb5'
			}
        }
        
    stage('SnykAnalysis') {
            steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			} 
       }
     }
}
