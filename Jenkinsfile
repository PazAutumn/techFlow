pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git credentialsId: '9547381d-6b8e-42fc-938c-9e06164d2e97', url: 'https://github.com/PazAutumn/techFlow.git'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Start server') {
            steps {
                sh 'json-server --watch db.json'
            }
        }
        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }
    }
}

