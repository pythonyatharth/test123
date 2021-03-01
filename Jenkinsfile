node {    
      def app     
      stage('Clone repository') {               
             
            checkout scm    
      }           stage('Build image') {         
       
            app = docker.build("docker1188/")    
       }           stage('Test image') {                       app.inside {            
             
             sh 'echo "Tests passed"'        
            }    
        }            stage('Push image') {
                                                  docker.withRegistry('https://hub.docker.com/u/docker1188', 'git') {                   app.push("${env.BUILD_NUMBER}")            
       app.push("latest")        
              }    
           }
        }
