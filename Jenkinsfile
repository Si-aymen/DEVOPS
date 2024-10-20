pipeline {
    agent any

    tools {
        maven 'M2_HOME' // Make sure this matches the name of the Maven installation in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Si-aymen/DEVOPS.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage ('Nexus'){
            steps {
                 sh 'mvn deploy';
             }
         }
    }

    post {
        success {
            echo 'Build and tests succeeded!'
        }
        failure {
            echo 'Build failed. Please check the logs.'
        }
    }
}
