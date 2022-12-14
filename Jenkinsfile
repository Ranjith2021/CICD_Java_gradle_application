pipeline {
    agent any

    tools {
    }

    stages {
        stage('sonar Quality Check') {
           agent {
            docker {
                image 'openjdk:11'
            }
           }   
            steps {
              withSonarQubeEnv(credentialsId: 'sonartoken') {
                sh 'chmod +x gradlew'
                sh './gradlew sonarqube'

                  }

            }


        }
    }
}
