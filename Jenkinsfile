
pipeline {
  agent any
  environment {
    NEW_VERSION = '1.3.0'
    SERVER_CREDENTIALS = credentials('server-credentials')
  }
  parameters{
    string(name: 'VERSION' , defaultValue: '', description: 'version to deploy on prod')
    choice(name: 'VERSION' , choices: ['1.1.0' , '1.2.0' ,'1.3.0'] ,description: '')
    booleanParam(name: 'executeTests' , defaultValue:true , description: '')
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
           params.executeTests
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
          echo "deploying versn ${params.VERSION}"
         
        }
      }
    }
     
   
}
