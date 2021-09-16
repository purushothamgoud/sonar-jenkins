pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Scan') {
      steps {
        withSonarQubeEnv(installationName: 'sonar-jenkins') { 
          sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:4.6.1.2450:sonar'
        }
      }
    }
  }
}
