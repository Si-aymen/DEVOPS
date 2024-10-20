pipeline {
    agent any

    tools {
        maven 'M2_HOME' // Ensure 'M2_HOME' is set up in Jenkins Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Si-aymen/DEVOPS.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Running Maven build
                    sh 'mvn clean install'
                }
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
