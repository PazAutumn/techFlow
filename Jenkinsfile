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
                script {
                    // Kill any existing process on port 3000 (if needed)
                    sh 'lsof -ti :3000 | xargs kill -9 || true'
                    
                    // Start json-server in the background
                    sh 'npx json-server --watch db.json --port 3000 &'
                    
                    // Wait 3 seconds for the server to start
                    sh 'sleep 3'
                    
                    // Verify server is running
                    sh 'curl -s http://localhost:3000/users || echo "Server not reachable"'
                }
            }
        }
        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }
        post {
            always {
                // Kill the server after tests (even if tests fail)
                sh 'lsof -ti :3000 | xargs kill -9 || true'
            }
        }
    }
}

