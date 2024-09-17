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
                sh 'apt-get update'
                sh 'apt-get install -y xvfb libgtk2.0-0 libgconf-2-4 libnss3 libasound2 libxtst6 libxss1 libgdk-pixbuf2.0-0 libgbm-dev libatk-bridge2.0-0'
                sh 'npm install --legacy-peer-deps'
            }
        }

        stage('Run Cypress Tests') {
            steps {
                sh 'xvfb-run npx cypress run'
            }
        }
        
    }
}