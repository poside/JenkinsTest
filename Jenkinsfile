stage('OWASP Dependency-Check Vulnerabilities') {
      steps {
        dependencyCheck additionalArguments: ''' 
                    -o './'
                    -s './'
                    -f 'ALL' 
                    --prettyPrint''', odcInstallation: 'OWASP-Dependancy-Test'
        
        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
      }
    }
