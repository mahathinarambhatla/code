pipeline {
    agent any
    tools {
        maven 'apache-maven-3.3.9'
    }
    stages {
        stage('Build') {
            steps {
                sh 'pwd'
                sh 'wget http://mirrors.jenkins.io/war-stable/latest/jenkins.war'
            }
         }
        stage('Artifact Upload')
        {
            steps{
            nexusArtifactUploader artifacts: [[artifactId: 'jenkins', classifier: '', file: 'jenkins.war', type: 'war']], credentialsId: 'nexus', groupId: 'com', nexusUrl: '35.231.84.239:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-releases', version: '1.0'


            }
        }
    }
}
