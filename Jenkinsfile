pipeline{
  agent{
    stages{
        stage('Deploy to GKE') {
            steps{
                script{
                    kubernetesDeploy(configs: "deployment.yaml", kubeconfigId: "kube-config2") 
                      }
                 }   
             }
          }
      }
}
