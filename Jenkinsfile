pipeline {
  agent any 
    stages{
        stage('Deploy to GKE') {
            steps{
                script{
                    kubernetesDeploy(configs: "deployment.yaml",kubeconfigId: "kubeconfig") 
                      }
                 }   
             }
          }
      }
