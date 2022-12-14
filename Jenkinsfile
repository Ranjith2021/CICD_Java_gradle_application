pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
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
