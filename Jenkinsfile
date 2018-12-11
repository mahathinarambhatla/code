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
            nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer-3.0.0.jar', classifier: '', file: 'bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: '6dcef9b8-246e-406b-8362-9b49dd420d39', groupId: 'bytecode-viewer', nexusUrl: '35.237.177.205:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-trial', version: '3.0.0'
            }
        }
    }
}
