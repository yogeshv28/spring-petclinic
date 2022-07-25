pipeline {
  agent any
  stages {
    stage('SCA') {
      agent {
        node {
          label 'windows'
        }

      }
      steps {
        withSonarQubeEnv(installationName: 'SonarQube', credentialsId: 'SonarTokenOne') {
          bat 'C:\\Users\\yogesh\\Jenkins\\sonar-scanner-cli-4.7.0.2747-windows\\sonar-scanner-4.7.0.2747-windows\\bin\\sonar-scanner -Dsonar.projectVersion=1.0 -Dsonar.projectKey=spring-app -Dsonar.sources=src -Dsonar.java.binaries=.'
        }

        waitForQualityGate(abortPipeline: true, credentialsId: 'SonarTokenOne')
      }
    }

  }
}