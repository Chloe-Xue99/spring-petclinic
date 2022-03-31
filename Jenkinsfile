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
        withSonarQubeEnv('Sonarqube') {
          sh './gradlew sonarqube'
        }

        waitForQualityGate true
      }
    }

  }
}