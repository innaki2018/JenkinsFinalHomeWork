pipeline {
  
  agent any
 
  triggers {
         pollSCM('* * 27-28 02 *') 
  }

  stages{
    stage ('clean') {
        steps {
            sh 'cd my-app; mvn clean'
        }

    } // clean
    stage ('compile'){
        steps {
            sh 'cd my-app; mvn compile'    
        }
        
    } // compile
    stage ('package'){
        steps {
            sh 'cd my-app; mvn package'
        }
        
    } // package
    
  } // stages
  
  post {
    success {
      mail to: "XXXXX@gmail.com", subject:"SUCCESS: ${JOBNAME}", body: "The build is passed."
    }
    failure {
      mail to: "XXXXX@gmail.com", subject:"FAILURE: ${JOBNAME}", body: "The build is failed."
    }
  } // post
 
    
}  // pipeline 
