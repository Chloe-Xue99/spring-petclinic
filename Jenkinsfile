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
        withSonarQubeEnv('sonarqube') {
          sh './mvnw clean package sonar:sonar'
        }

      }
    }

    stage('Execute') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}