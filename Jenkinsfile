pipeline{
  agent{
     kubernetes{
          defaultContainer 'kubedemo'
       yaml { 
          apiVersion: apps/v1
          kind: Deployment
          metadata: 
           name: kubedemo
          spec: 
           replicas: 2
           selector: 
            matchLabels: 
             bb: web
          template: 
           metadata: 
            labels: 
             bb: web
           spec: 
            containers: 
              image: gaya3sudhi/dockerapp
              name: kubedemo
         
         }
       }
  }
   stages{           
       stage('stage-1') {
           steps{
                 sh "echo In stage one"
                }
             }
    stage('stage-2') {
           steps{
                 sh "echo In stage two"
               }
           }
    stage('stage-3') {
    steps{
             sh "echo In stage three"
        }
      }
    }
   }

    
