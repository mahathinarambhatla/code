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
            nexusArtifactUploader artifacts: [[artifactId: 'sample', classifier: '', file: 'jenkins.war', type: 'war']], credentialsId: '882f6950-51f0-4369-aed1-9ecbee145518', groupId: 'sample', nexusUrl: '35.237.177.205:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0'

            }
        }
    }
}
