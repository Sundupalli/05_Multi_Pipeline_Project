node
{
def mavenHome = tool name:'maven3.8.6'

     
     stage('Pull the code')
     {
            git branch: 'development', credentialsId: '4ea161c0-f0e2-4e5a-ad7f-28e909d552c0', url: 'https://github.com/Sundupalli/02-maven-web-application.git'
     }

     stage('Build artifacts')
     {
           sh "${mavenHome}/bin/mvn clean package"        
     }

     stage('Execute SonarQube Report')
     {
           sh "${mavenHome}/bin/mvn sonar:sonar"  
     }

     stage('Uploads Artifacts into Nexus')
     {
           sh "${mavenHome}/bin/mvn deploy"  
     } 
/*
     stage ('Deploy App Into Tomcat')
     {
          sshagent(['6eec5fdd-055c-4f1e-a564-4379d617ccfd']) 
          {
               sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.6.126.151:/opt/apache-tomcat-9.0.65/webapps"
          }
     }

     stage ('Send Email Notification')
     {
          mail bcc: '', body: '''Hi Reddy Sekhar



Job is done sucessuflly....

Regards,successfully
Reddy Sekhar
+91 8553322492''', cc: 'reddysekhar050@gmail.com', from: '', replyTo: '', subject: 'Build over', to: 'sendmeanemail208@gmail.com'     
     }
*/  
}
