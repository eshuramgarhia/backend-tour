pipeline {
    agent any

    tools {
        nodejs "node"   // Use your Jenkins NodeJS version name
    }

    stages {

        stage('Checkout') {
            steps {
                echo "Fetching latest code..."
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing dependencies..."
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo "Building backend..."
                sh 'npm run build'   // many backend APIs don't have build step
            }
        }

        stage('Start Server') {
            steps {
                echo "Starting Node server..."
                sh 'node server.js &'
            }
        }
    }

    post {
        success {
            echo "Backend pipeline executed successfully!"
        }
        failure {
            echo "Backend pipeline failed!"
        }
    }
}

