pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Add  build steps 
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // Add test steps 
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add  deploy steps 
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished!'
        }
    }
}
