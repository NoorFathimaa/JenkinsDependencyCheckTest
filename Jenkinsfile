pipeline {
  agent any
  stages {
    stage('Checkout SCM') {
      steps {
	git 'https://github.com/NoorFathimaa/JenkinsDependencyCheckTest'
             }
    }
    stage('OWASP DependencyCheck') {
      steps {
	dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
    }
  }
  post {
      success {
        dependencyCheckPublisher pattern: 'dependency-check-report.xml'
      }
    }
 }
