pipeline {
    agent any
    tools {
        maven 'M2_HOME'      }
    stages {
        stage('GIT') {
            steps {
                git branch: 'main',  
                    url: 'https://github.com/Si-aymen/DEVOPS.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'  
            }
        }
    }
}
