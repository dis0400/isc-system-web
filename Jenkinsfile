pipeline {
    agent any
    tools {
        nodejs 'node-20'
    }
    stages {
        stage('Clone Project') {
            steps {
                git 'https://github.com/dis0400/isc-system-web.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'sudo apt-get update'
                sh 'sudo apt-get install -y xvfb'
                sh 'npm install'
            }
        }

        stage('Run Cypress Tests') {
            steps {
                sh 'xvfb-run npx cypress run'
            }
        }
        
    }
}