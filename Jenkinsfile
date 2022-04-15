pipeline {
    agent any
    stages {
        
        stage('build') {
            steps {
                git branch: 'main', credentialsId: '48c2ce83-0fb4-4887-94fa-3b2732b72cce', url: 'https://github.com/Chloe-Xue99/spring-petclinic.git'
                sh 'mvn package'
            }
        }
        
        
        
        stage('Deploy') {
            steps {
                ansiblePlaybook credentialsId: '28d22200-c0e7-4389-a7f7-b61cd9c9d168', disableHostKeyChecking: true, installation: 'ansible', inventory: '/var/lib/jenkins/workspace/test_2/hosts', playbook: '/var/lib/jenkins/workspace/test_2/playbook.yaml'
            }
        }
    }
}
