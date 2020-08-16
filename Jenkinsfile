pipeline {
  agent any 
    stages{
        stage('Deploy to GKE') {
            steps{
                script{
                    kubernetesDeploy(kubeconfigId: "sprint6-kube", configs: "deployment.yaml", enableConfigSubstitution: true) 
                      }
                 }   
             }
          }
      }
