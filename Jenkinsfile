
pipeline {
  agent any
  environment {
    NEW_VERSION = '1.3.0'
    SERVER_CREDENTIALS = credentials('server-credentials')
  }
 
  
    stages {
      stage("build"){
        when
        {
          expression {
            BRANCH_NAME =='main' || CODE_CHANGES == TRUE
          }
        }
        steps{
          echo "building the applications. .."
          echo "Building version ${NEW_VERSION}"
          
        }
      }
      stage("test"){
        when
        {
          expression {
            BRANCH_NAME == 'main' || BRANCH_NAME == 'master'
          }
        }
        steps{
          echo "testing the application"
        }
      }
      stage("deploy"){
        steps{
          echo "deploying the applications "
          echo "delpoying with ${SERVER_CREDENTIALS}"
         
        }
      }
    }
     
   
}
