pipeline 
{
    agent any
    tools
    {
        jdk "java11"
        maven "maven3"
    }
    stages 
    {
        stage('code fetch') 
        {
            steps 
            {
               echo "code fetch from github repo"
               git branch: 'main', url: 'https://github.com/harshthakkar2611/maven-devopsstar.git'
            }
        }
        stage('build code') 
        {
            steps 
            {
                echo "build process"
                sh 'mvn clean package'
            }
        }
        stage('archieve artifact') 
        {
            steps 
            {
                echo "artifact archieved"
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
        stage('build other job') 
        {
            steps 
            {
                echo "other job build started"
                build wait: false, job: 'deploy-pipeline'
            }
        }
    }
}
