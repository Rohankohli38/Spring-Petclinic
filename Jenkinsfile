pipeline {
    agent any

    stages {
       stage ('Build') {
          steps {
              sh 'mvn clean'
          }
       }
       stage ('Compile') {
          steps {
              sh 'mvn compile'
              sh "export AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE"
              // Example of a hardcoded AWS Secret Key
              sh "export AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY"
          }
       }
       stage ('SonarQube analysis') {
          steps {
         withSonarQubeEnv(credentialsId: 'Sonar_Jenkins', installationName: 'SonarCloud') { // You can override the credential to be used
           sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=myproject38'
          }
         }
       } 
    }
}

