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
          }
       }
       stage ('SonarQube analysis') {
          steps {
         withSonarQubeEnv(credentialsId: 'Sonar_Jenkins', installationName: 'SonarCloud') { // You can override the credential to be used
           sh 'mvn clean sonar:sonar -Dsonar.projectKey=myproject38'
          }
         }
       } 
    }
}

