node('master')
{
    stage('CD')
    {
    git 'https://github.com/selenium-saikrishna/maven.git'
    }
    stage('CB')
    {
    sh 'mvn package'
    }
     stage('CDeploy')
    {
      sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@172.31.52.141:/var/lib/tomcat8/webapps/qaapp.war'
    }
     stage('CT')
    {
     git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
     sh 'java -jar /home/ubuntu/.jenkins/workspace/Pipeline/testing.jar'
    }
    stage('CDeploy1')
    {
      sh 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@172.31.54.6:/var/lib/tomcat8/webapps/prodapp.war'
    }
    
    
}
