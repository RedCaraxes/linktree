pipeline {
    agent any

    tools {
        maven 'M398'  // Nombre configurado en Jenkins > Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    credentialsId: 'github-credentials-id', 
                    url: 'https://github.com/RedCaraxes/linktree.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
