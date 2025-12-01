pipeline {
    agent any

    tools {
        nodejs 'Node'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build Project') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Start Server') {
            steps {
                bat 'npm start'
            }
        }
    }
}
