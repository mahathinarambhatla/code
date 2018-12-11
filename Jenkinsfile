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
            nexusArtifactUploader {
                nexusVersion('nexus3')
                protocol('http')
                nexusUrl('10.1.227.16:8081')
                 groupId('bytecode-viewer')
                 version('3.0.0')
                repository('maven-trial')
                credentialsId('6dcef9b8-246e-406b-8362-9b49dd420d39')
                artifact {
                 artifactId('nexus-artifact-uploader')
                    type('jar')
                    classifier('debug')
                    file('bytecode-viewer-3.0.0.jar')
                  }
                }
            }
        }
    }
}
