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
             sh 'cp -R /root/.jenkins/workspace/dpipeline/target/* /opt/apache-tomcat-8.5.3/webapps'
         }
     }
        
    }
}
