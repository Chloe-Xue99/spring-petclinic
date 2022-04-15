pipeline {
    agent any
    stages {
        
        stage('build') {
            steps {
                git branch: 'main', credentialsId: '48c2ce83-0fb4-4887-94fa-3b2732b72cce', url: 'https://github.com/SwaggieHu/spring-petclinic.git'
                sh 'mvn package'
            }
        }
        
        
        
        stage('Deploy') {
            steps {
                ansiblePlaybook credentialsId: '6d71f0a0-eeaf-426c-81d7-6066314d70ae', disableHostKeyChecking: true, installation: 'ansible', inventory: '/var/lib/jenkins/workspace/test_2/hosts', playbook: '/var/lib/jenkins/workspace/test_2/playbook.yaml'
            }
        }
    }
