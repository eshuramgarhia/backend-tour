pipeline {
    agent any

    environment {
        NODE_HOME = nodejs // Node install path jithon Jenkins node access kare
        PROJECT_DIR = '.' // Project root folder
    }

    stages {
        stage('Checkout') {
            steps {
                // Git repository pull karna
                git branch: 'main', url: 'https://github.com/username/your-node-backend.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Node dependencies install karna
                    sh 'npm install'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    // Agar test scripts available ne
                    sh 'npm test'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Agar build script hai
                    sh 'npm run build'
                }
            }
        }

        stage('Start Server') {
            steps {
                script {
                    // Backend server start karna
                    sh 'nohup npm start &'
                    echo "Server started successfully!"
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs!'
        }
    }
}
