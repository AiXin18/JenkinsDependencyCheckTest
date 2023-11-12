pipeline {
  agent any 
  stages {
    stage('pre-echo') {
      steps {
        echo 'pre-echo'
      }
    }
    stage('OWASP-Dependency-Check Vulnerabilities') {
      steps {
        dependencyCheck additionalArguments: ''' 
                    -o './'
                    -s './'
                    -f 'ALL' 
                    --prettyPrint''', odcInstallation: 'OWASP-Dependency-Check Vulnerabilities'
        
        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
        echo 'OWASP-Dependency-Check Vulnerabilities'
      }
    }
  }
}