// Jenkinsfile
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
    }
    post {
        always {
            junit '*.xml' // Ensure this path matches your actual reports location
        }
    }
}
