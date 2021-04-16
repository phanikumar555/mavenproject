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
    
}
