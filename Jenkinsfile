pipeline {
    agent any
    stages {
        
        stage('build') {
            steps {
                sh 'mvn package'
            }
        }
        
        
        
        stage('Deploy') {
            steps {
                ansiblePlaybook credentialsId: 'c3e8c905-4051-4477-99ba-bdfba4bca3d4', disableHostKeyChecking: true, installation: 'ansible', 
                    inventory: '/var/lib/jenkins/workspace/spring-petclinic-a2_main/hosts', 
                    playbook: '/var/lib/jenkins/workspace/spring-petclinic-a2_main/playbook.yaml'
            }
        }
    }
}
