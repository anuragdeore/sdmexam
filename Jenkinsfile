CODE_CHANGES = getGitChanges()
pipeline {
  agent any
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
        }
      }
    }
     
   
}
