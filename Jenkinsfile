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
    stage ('execute'){
      steps {
          sh 'cd my-app; java -cp target/classes com.mycompany.app.App'
      }
    }
    
  } // stages
  
  post {
    success {
      sh 'echo "The build is passed successfully." '
    }
    failure {
      sh 'echo "The build is failed." '
    }
  } // post
 
    
}  // pipeline 
