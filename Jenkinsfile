pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./mvnw package
java -jar target/*.jar'''
      }
    }

    stage('Sonarqube Analysis') {
      steps {
        withSonarQubeEnv('sonarqube') {
          sh './mvnw clean package sonar:sonar'
        }

      }
    }

  }
}