pipeline
{
    agent any 
    
    stages
    {
     
     stage ('compile code')
     {
         steps
         {
             sh 'mvn clean install'
         }
     }
     stage ('test')
     {
         steps
         {
             sh 'mvn test'
         }
     }
    
     stage ('deploy')
     {
         steps
         {
             sh 'cp -R /root/.jenkins/workspace/descriptive/target/* /opt/apache-tomcat-8.5.3/webapps'
         }
     }
    }
      post 
    {
        always
        {
            slackSend channel: '#jenkins',                
                message: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URL}"
        }
    }   
}
