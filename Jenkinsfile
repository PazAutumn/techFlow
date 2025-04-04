pipeline {
    agent any
    tools {
        nodejs 'NodeJS' // Nombre configurado en Global Tool Configuration
    }
    stages {
        stage('Clone repository') {
            steps {
                git credentialsId: 'techFlow', url: 'https://github.com/PazAutumn/techFlow.git'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
                sh 'ls node_modules/.bin/json-server || echo "json-server not found!"'
            }
        }
        stage('Start server') {
            steps {
                sh 'npx json-server --watch db.json'
            }
        }
        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }
    }
}

