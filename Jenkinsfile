node
{
   def MavenHome=tool name:"maven3.6.3"
    stage('CheckoutCode')
    {
        git branch: 'development', credentialsId: '643d233f-9730-459c-b55a-62c925577924', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
    }
    
    stage('Build')
    {
   sh "${MavenHome}/bin/mvn clean package" 
    }
   
   stage('DeployAppIntoTomcatServer')
    {
sshagent(['6a0be0c4-6c70-43d9-bf99-9c6b59e9084a'])
sh "scp target/maven-web-application.war ec2-user@65.2.171.70:/opt/apache-tomcat-9.0.73/webapps/"
    }
 
 }
