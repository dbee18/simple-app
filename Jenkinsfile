pipeline {
   agent any
   tools {
             maven 'maven3'
         }
    
    stages{
                 stage('Build'){
                     steps{
                         // mvn clean package
                          //sh script: 'mvn clean package'
                          //archiveArtifacts artifacts: 'target/*.war', onlyIfSuccessful: true
                         sh 'mvn clean package'      
                     }
                 }

                 stage('War upload to Nexus'){
                     steps{
                         //sh 'mvn clean package'  http://13.233.157.98:8081/
                         nexusArtifactUploader artifacts: [
                            [artifactId: 'simple-app', classifier: '', file: 'target/simple-app-1.0.0.war', type: 'war']
                          ],
                            credentialsId: 'nexus3', 
                            groupId: 'in.javahome', 
                            nexusUrl: '172.31.13.94',
                            nexusVersion: 'nexus3',
                            protocol: 'http',
                            repository: 'http://13.233.157.98:8081/repository/simpleapp-release',
                            version: '1.0.0'
                     }
                 }


    }
}
