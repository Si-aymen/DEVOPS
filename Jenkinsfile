pipeline {

agent any


stages {

stage('GIT') {

           steps {

               git branch: 'master',

               url: 'https://github.com/Si-aymen/DEVOPS'

          }

     }

stage ('Compile Stage') {

    steps {

        sh 'mvn clean compile'

    }

}
stage ('SonarQube') {

    steps {

        sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=Aymenrahali@6631* -Dmaven.test.skip=true';

    }

}

}

}
