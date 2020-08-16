pipeline {
  agent any 
    stages{
        stage('Deploy to GKE') {
            steps{
                  echo "Deployment started"
			step([$class: 'KubernetesEngineBuilder', projectId: 'wired-rex-283811', 
			clusterName: 'cluster-1', location: 'us-east1-b', manifestPattern: 'deployment.yaml',
			credentialsId: 'sprint6-kube', verifyDeployments: true])
			echo "Deployment Finished"
                 }   
             }
          }
      }
