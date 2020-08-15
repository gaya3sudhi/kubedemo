pipeline {
  agent any 
    stages{
        stage('Kubernetes Setup'){
        try{
            sh("kubectl create -f app-deployment.yml -v=8")
        } 
        }
      
    }
}
