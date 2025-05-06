pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS'
    }
    
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/DariaHalchenko/pipeline.git', branch: 'main'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Run Application') {
            steps {
                sh 'node app.js &'
                sh 'sleep 5'
                sh 'curl http://localhost:3000'
            }
        }
    }
}
