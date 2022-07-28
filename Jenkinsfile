pipeline {
    agent { lable "agentfarm" } 

    stages {
       stage ('Build') {
          steps {
              mvn clean
          }
       }
    }
}
