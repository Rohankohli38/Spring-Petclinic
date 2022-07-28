pipeline {
    agent { label "agentfarm" } 

    stages {
       stage ('Build') {
          steps {
              sh 'mvn clean'
          }
       }
    }
}
