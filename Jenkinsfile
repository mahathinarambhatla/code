pipeline 
{
  agent any
  tools {
    nodejs "node"
    maven 'apache-maven-3.3.9'
  }  
  stages 
  {      
    stage('Maven Build') {
      when {
          sh 'find . -name pom.xml'
         }
         steps {
                sh 'mvn clean package'
            }
        steps{
            nexusArtifactUploader artifacts: [[artifactId: 'bytecode-viewer', classifier: '', file: 'target/bytecode-viewer-3.0.0.jar', type: 'jar']], credentialsId: 'nexus', groupId: 'the.bytecode.club', nexusUrl: '35.231.84.239:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-trial', version: '3.0.0'
            }
         }
     stage('Build NPM Code') 
      {
         when {
          sh 'find . -name package.json'
         }
       steps{
         sh 'cp .npmrc /var/lib/jenkins'
         sh 'npm install'
         sh 'npm publish'
        }
       }
       }
     } 
