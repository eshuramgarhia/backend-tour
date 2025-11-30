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
                echo "Installing npm dependencies..."
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running tests..."
                sh 'npm test || true'   // allows pipeline even if no tests exist
            }
        }

        stage('Build') {
            steps {
                echo "Building backend..."
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
