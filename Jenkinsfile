pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/tu_usuario/tu_repositorio.git'
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
            steps {
                sh 'npm test > test-results.txt'
            }
        }
    }
}