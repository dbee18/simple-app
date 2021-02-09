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

                stage('war upload to Nexus'){
                     steps{
                         sh 'mvn clean package'      
                     }
                 }


    }
}
