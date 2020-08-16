pipeline {
  agent any 
    stages{
        stage('Deploy to GKE') {
            steps{
                script{
                    kubernetesDeploy(kubeconfigId: "kubeconfig-new", configs: "deployment.yaml", enableConfigSubstitution: true) 
                      }
                 }   
             }
          }
      }
