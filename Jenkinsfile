pipeline {
    agent any

    tools {
        maven 'M2_HOME' // Ensure 'M2_HOME' matches the Maven installation name in Jenkins
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

        stage('Nexus') {
            steps {
                // Deploying artifacts to Nexus using credentials from Jenkins
                withCredentials([usernamePassword(credentialsId: 'nexus-credentials-id', 
                                  usernameVariable: 'USERNAME', 
                                  passwordVariable: 'PASSWORD')]) {
                    sh """
                    mvn deploy -DskipTests \
                        -Dnexus.username='admin' \
                        -Dnexus.password='Omen15@6631'
                    """
                }
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
