pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''./mvnw package

cp -r ./target /home/vagrant/target'''
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