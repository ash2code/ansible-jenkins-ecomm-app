pipeline {
    agent any 

    stages {
        stage('code-checkout') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/ash2code/ansible-jenkins-ecomm-app.git'
                }
            }
        }
        stage('playbook-syntax') {
            steps {
                script {
                    sh "ansible-playbook -i hosts ecomm-playbook.yaml --syntax-check" 
                }
            }
        }
        stage('playbook-run') {
            steps {
                script {
                    sh "ansible-playbook -i hosts ecomm-playbook.yaml"
                }
            }
        }
    }
}
