pipeline{
  agent{
     kubernetes{
        label mylabel
        defaultContainer 'kubedemo'
       yaml ---
          apiVersion: apps/v1
          kind: Deployment
          metadata: 
           name: kubedemo
           namespace: default
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
             - 
              image: gaya3sudhi/dockerapp
              name: kubedemo
           --- 
           apiVersion: v1
           kind: Service
           metadata: 
             name: kubedemo
             namespace: default
           spec: 
             ports: 
               - 
                 port: 8009
                 targetPort: 8080
             selector: 
               bb: web
             type: LoadBalancer
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

    
