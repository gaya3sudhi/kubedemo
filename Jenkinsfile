pipeline {
  agent any 
    stages{
        stage('Deploy to GKE') {
            steps{
                script{
                    kubernetes(configs: "deployment.yaml") 
                      }
                 }   
             }
          }
      }
