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
            nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer', classifier: '', file: ' /var/lib/jenkins/workspace/maven-trial/target/bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: 'baf54de6-ae59-467c-8302-cdd09514b531', groupId: 'the.bytecode.club', nexusUrl: '10.1.227.16:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-trial', version: '3.0.0'

            }
        }
    }
}
