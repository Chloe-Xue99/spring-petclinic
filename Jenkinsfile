pipeline {
  agent {
    node {
      label 'spring-petclinic-a1'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Sonarqube Analysis') {
      steps {
        withSonarQubeEnv(installationName: 'sonarqube', envOnly: true)
        waitForQualityGate true
      }
    }

  }
}