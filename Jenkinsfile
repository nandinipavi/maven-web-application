node{
  
  def mavenHome = tool name: 'maven 3.9.5'  
  
  echo "Node name is: ${env.NODE_NAME}"
  echo "Job name is: ${env.JOB_NAME}"
  echo "Build Number is: ${env.BUILD_NUMBER}"
  
  stage('CheckoutCode')
  {
    git branch: 'development', credentialsId: 'edad5bc0-51c9-41ce-a733-62e66bcf9d6e', url: 
	'https://github.com/nandinipavi/maven-web-application.git'
  }
  stage('Build')
  {
    sh "${mavenHome}/bin/mvn clean package"
  }
  /*
  stage('ExecuteSonarQubeReport')
  {
    sh "${mavenHome}/bin/mvn clean sonar:sonar"
  }
  stage('UploadArtifactIntoNexus')       
  {
    sh "${mavenHome}/bin/mvn clean deploy"
  }
  stage('DeployAppIntoTomcatServer')
  {
  sshagent(['eb9f9aab-2c91-489f-87c8-9223334e73da']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.0.196:/opt/apache-tomcat-9.0.80/webapps/"
   }
  }
  */
  }
