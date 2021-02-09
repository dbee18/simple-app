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
       
       stage('upload war to naxus'){
            steps{
                sh 'mvn clean package'            
            }
        }

    }
}
