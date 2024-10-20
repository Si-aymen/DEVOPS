pipeline {
    agent any

    tools {
        maven 'M2_HOME' // Ensure that 'M2_HOME' matches the Maven installation name in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Cloning the Git repository from the master branch
                git branch: 'master', url: 'https://github.com/Si-aymen/DEVOPS.git'
            }
        }

        stage('Build') {
            steps {
                // Running the Maven build
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Running Maven tests
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
