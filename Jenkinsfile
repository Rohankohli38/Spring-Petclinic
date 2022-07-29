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
       stage ('SonarQube analysis') {
          steps {
              withSonarQubeEnv('SonarCloud') {
              sh 'mvn sonar:sonar'
                }
          }

      }  
    }
}
