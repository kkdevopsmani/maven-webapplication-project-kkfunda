


node 
{
   //     /var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/maven-3.9.16/bin

   def mavenHome=tool name: "maven-3.9.6"
  stage('git checkout')
  {
      git branch: 'dev', url: 'https://github.com/kkdevopsmani/maven-webapplication-project-kkfunda.git'
  }
  stage('compile')
  {
   sh "${mavenHome}/bin/mvn compile"
  }
   stage('Build')
  {
   sh "${mavenHome}/bin/mvn clean package"
  }
   */stage('SQ REPORT')
  {
   sh "${mavenHome}/bin/mvn sonar:sonar"
  }*/
  stage('Deploy Artifact')
  {
   sh "${mavenHome}/bin/mvn deploy"
  }


    stage('Deploy to Tomcat') 
    {
      
      sh """

      curl -u admin:password \
--upload-file /var/lib/jenkins/workspace/airtel_pipeline_way/target/maven-web-application.war \
"http://3.110.104.66:8080/manager/text/deploy?path=/maven-web-application&update=true"
          
        """
    }
}  // node ending
