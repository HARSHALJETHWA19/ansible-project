pipeline {
    agent any 
    stages {
      stage('SCM Checkout') {
        steps {
           checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/HARSHALJETHWA19/ansible-project.git']]])          }
      }  
      stage('Execute Ansible') {
        steps {
           ansiblePlaybook credentialsId: 'ansible', disableHostKeyChecking: true, installation: 'ansible-copsc', inventory: 'hosts', playbook: 'web-nginx.yml'        }  
      }
    }
}

