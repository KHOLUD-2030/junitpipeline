pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your GitHub repository
                git branch: 'main', url: 'https://github.com/KHOLUD-2030/junitpipeline.git'
            }
        }
        stage('Build') {
            steps {
                // Run Maven build
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                // Run unit tests
                sh 'mvn test'
            }
        }
        stage('Debug') {
            steps {
                // List files to verify directory structure
                sh 'ls -R'
                // List contents of target/surefire-reports to check if reports are generated
                sh 'ls target/surefire-reports || true'
            }
        }
    }
    post {
        always {
            // Archive the test results
            junit 'target/surefire-reports/*.xml' // Ensure this path matches your actual reports location
        }
    }
}
