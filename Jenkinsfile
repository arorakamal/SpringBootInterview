pipeline {
  agent any
  tools { 
        maven 'Maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=arorakamal -Dsonar.organization=arorakamal -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=ce5056eb245049dd528994206b023e6cec243cb5'
			}
        } 
  }
}
