pipeline {
    agent any 
    stages {
        stage('checkout') { 
            steps {
             git 'https://github.com/spring-projects/spring-petclinic.git'

            }
        }
        stage('Build&Code Quality') { 
            steps {
          withSonarQubeEnv('SonarQube') {
                 sh 'mvn clean package sonar:sonar' 
            }
        }
        }
        stage('Junit') { 
            steps {
              junit 'target/surefire-reports/*.xml'
  
            }
        }
        
    }
}
