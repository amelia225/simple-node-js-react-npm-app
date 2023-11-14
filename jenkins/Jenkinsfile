pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
      steps {
        echo 'test'
      }
    }

    stage('OWASP DependencyCheck') {
      steps {
         dependencyCheck additionalArguments: ''' 
                    -o './'
                    -s './'
                    -f 'ALL' 
                    --prettyPrint''', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
        
        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
      }
    }
  }  
}