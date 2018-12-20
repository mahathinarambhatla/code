pipeline 
{
  agent any
  tools {
    nodejs "node"
     }
 stages 
  {      
    stage('NPM Build') {
      when { expression { return fileExists('package.json')}}
        steps {
               sh 'npm install'
               }
    }
     stage ('OWASP publish')
            {
              steps
              {
              dependencyCheckAnalyzer datadir: '', hintsFile: '', includeCsvReports: true, includeHtmlReports: true, includeJsonReports: true, includeVulnReports: true, isAutoupdateDisabled: true, outdir: '', scanpath: ' ${WORKSPACE}', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: ''
            dependencyCheckPublisher()
              }
            }
  }        
 }
