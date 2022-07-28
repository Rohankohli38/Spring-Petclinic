pipeline {
    agent { label "agentfarm" } 

    stages {
       stage ('Build') {
          steps {
              mvn clean
          }
       }
    }
}
