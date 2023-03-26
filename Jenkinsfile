pipeline {
    agent any 
    stages {
        stage("sonar quality check") {
            agent {
                docker {
                    image 'adoptopenjdk/openjdk11'
                }
            }

            steps {
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                    }
                    
                }
            }
        }
    }
}