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
              sh "export aws_access_key=123456kwqvcuw"
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

