pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('Sonarqube Analysis') {
      steps {
        withSonarQubeEnv 'sonarqube'
        waitForQualityGate true
      }
    }

    stage('End') {
      steps {
        sleep(time: 100, unit: 'DAYS')
      }
    }

  }
}