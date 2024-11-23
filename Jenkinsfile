pipeline {
  agent any
  tools { 
        maven 'Maven_3_2_5'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=devsecops-buggyapp_testing -Dsonar.organization=devsecops-buggyapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=9be7e0831cf6ea39cee51ea57031e5ea2a221bbb'
			}
        } 
  }
}
