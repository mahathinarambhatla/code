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
            nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer', classifier: '', file: 'target/bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: '882f6950-51f0-4369-aed1-9ecbee145518', groupId: 'the.bytecode.club', nexusUrl: '35.237.177.205:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '3.0.0'

            }
        }
    }
}
