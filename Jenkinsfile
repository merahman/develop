pipeline {

    agent {label 'slave'}
	tools { 
        maven 'Apache Maven 3.6.0'
    }
	stages {
		stage ('Compile and Build') {
            steps {
            sh  'mvn -f ./MasterPipeline/Bom/pom.xml clean install package'
            }
		}
		
		
        
    stage('SonarQube analysis') {
      steps {
    withSonarQubeEnv('SONAR_SERVER_1') {
      //requires SonarQube Scanner for Maven 3.3+
      sh 'mvn -f ./MasterPipeline/Bom/pom.xml org.sonarsource.scanner.maven:sonar-maven-plugin:3.2:sonar'
    }
    }
    }
	
    
    
    
        
        
    }

}