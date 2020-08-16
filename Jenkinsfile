pipeline {
        agent any
        environment {
            dockerImage = ''
		PROJECT_ID = 'wired-rex-283811'
 		CLUSTER_NAME = 'cluster-1'
 		LOCATION = 'us-east1-b'
 		CREDENTIALS_ID = 'sprint6-kube'
                    }
		
	 stages {	
		   stage('Scm Checkout') {            
			steps {
	                  checkout scm
			      }	
	                  }
	           
		   stage('Build') { 
	                steps {
	                  script {
                                 myapp = docker.build("gaya3sudhi/sprint6demo")
                                 }
	                     }
	                 }
		   stage('Test') { 
			steps {
		          script {
                                  docker.withRegistry('https://registry.hub.docker.com', 'docker-cred') {
                                  myapp.push("latest")
                                  myapp.push("${env.BUILD_ID}")
                                 }
			      }
		         }
		   stage('Build Docker Image') { 
			steps {
	                   script {
	                      dockerImage = docker.build registry + ":$BUILD_NUMBER"
	                          }
	                      }
		         }
            stage('Deploy Image') {
                steps{
                    script {
                    docker.withRegistry( '', registryCredential )
			      {
                        dockerImage.push()
                              }
                          }
                       }
	           }
	           stage('Deploy to GKE') {
 			steps{
 				echo "Deployment started"
				sh 'ls -ltr'
				sh 'pwd'
				sh "sed -i 's/tagversion/${env.BUILD_ID}/g' deployment.yaml"
				step([$class: 'KubernetesEngineBuilder', projectId: env.PROJECT_ID,
				 clusterName: env.CLUSTER_NAME, location: env.LOCATION, manifestPattern: 'deployment.yaml',
				 credentialsId: env.CREDENTIALS_ID, verifyDeployments: true])
				echo "Deployment Finished"
 	                     }
	                }
	          }
	    }
