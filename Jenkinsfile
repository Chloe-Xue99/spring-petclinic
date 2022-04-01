pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./mvnw package

cp -r ./target ~/target'''
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