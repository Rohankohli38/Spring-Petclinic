pipeline {
    agent { label "agentfarm" } 

    stages {
       stage ('Build') {
          steps {
              sh 'mvn clean'
          }
       }
       stage ('Compile') {
          stpes {
              sh 'mvn compile'
          }
       } 
       stage ('Test') {
          steps {
              sh 'mvn test'
          }  
       }
    }
}
