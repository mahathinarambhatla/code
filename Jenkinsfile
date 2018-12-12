pipeline {
    agent any
    tools {
        maven 'apache-maven-3.3.9'
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
         }
        stage('Artifact Upload')
        {
            steps{
            nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer', classifier: '', file: 'target/bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: 'nexus', groupId: 'the.bytecode.club', nexusUrl: '35.231.84.239:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-trial', version: '3.0.0'
            }
        }
    }
}
