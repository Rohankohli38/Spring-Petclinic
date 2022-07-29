pipeline {
    agent { label "agentfarm" } 

    stages {
       stage ('Build') {
          steps {
              sh 'mvn clean'
          }
       }
       stage ('Compile') {
          steps {
              sh 'mvn compile'
          }
       } 
       stage ('Test') {
          steps {
              sh 'mvn test'
          }  
       }
       stage ('SonarQube analysis') {
         withSonarQubeEnv(credentialsId: '52e367c09606813078a675d5a843138cd16f0b4d', installationName: 'My SonarQube Server')
      sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
    }
}
}
