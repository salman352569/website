pipeline {
      agent any
      

      stages {
          
          stage('Build') {
                
                steps {
                     
                     sh 'docker build -t website .'
                }
              }
 
           stage('Test') {
               
               steps {
                   
                   sh 'docker rm -f test || true'
                   sh 'docker run -d --name test -p 8082:80 website'
                   sh 'sleep 5'
                   sh 'docker ps'
                   sh 'docker rm -f test'
            }

        }
           stage('Production') {

                steps {
                   sh 'docker rm -f prod || true'
                   sh 'docker run -d --name prod -p 5000:80 website'
            
        
    }
}
