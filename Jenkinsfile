node('master') 
{
    stage('ContinuousDownload-master')
    {
        git 'https://github.com/intelliqittrainings/maven.git'             
    }
    stage('ContinuousBuild-master')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment-master')
    {
sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.23.20:/var/lib/tomcat9/webapps/testapp.war'
    }

    stage('ContinuousTesting-master')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
    stage('ContinuousDelivery-master')
    {
    
    sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.28.60:/var/lib/tomcat9/webapps/prodapp.war'}
}
