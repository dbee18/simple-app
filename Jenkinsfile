pipeline {
   agent any
   tools {
              maven 'Maven-3.6.3'
         }
   options {
                buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '5', numToKeepStr: '7')
         }
    
    stages{
                  /**
                  stage("checkout git"){
                        steps{
                           git 'https://github.com/dbee18/simple-app.git'
                        }
                    }**/

                 stage('Build krooo'){
                     steps{
                         sh 'mvn clean package'      
                     }
                 }
                 /***
                 stage('War upload to Nexus'){
                     steps{
                          script{
                              def mavenPom = readMavenPom file: 'pom.xml'
                              def nexusRepoName = mavenPom.version.endsWith("SNAPSHOT") ? "simpleapp-snapshot" : "simpleapp-release"
                         nexusArtifactUploader artifacts: [
                            [
                               artifactId: 'simple-app',
                               classifier: '', 
                               //file: 'target/simple-app-${mavenPom.version}.war',
                               file: "target/simple-app-${mavenPom.version}.war",
                               type: 'war'
                            ]
                          ],
                            credentialsId: 'nexus3', 
                            groupId: 'in.javahome', 
                            nexusUrl: '13.233.157.98:8081',
                            nexusVersion: 'nexus3',
                            protocol: 'http',
                            repository: nexusRepoName,
                            version: "${mavenPom.version}"
                          }   
                     }
                 }
                **/

    }
}
