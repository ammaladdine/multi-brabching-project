node
  {
  stage('checkout')
    {
     checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], gitTool: 'achyuth501', userRemoteConfigs: [[credentialsId: 'multi-project', url: 'https://github.com/ammaladdine/multi-brabching-project.git']]]) 
    }
  stage('deploy')
    {
    echo 'branch name ' + env.BRANCH_NAME
    
    if (env.BRANCH_NAME.startsWith("Feature_"))
      {
      echo "Deploying to Dev environment after build"
      }
      
    else if (env.BRANCH_NAME.startsWith("Release_"))
      {
      echo "Deploying to Stage after build and Dev Deployment"
      }
      
    else if (env.BRANCH_NAME.startsWith("master"))
      {
      echo "Deploying to PROD environment"
      }
      
    sh """
    echo "build success"
    """
    }
}
