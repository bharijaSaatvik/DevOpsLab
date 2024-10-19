pipeline{
    agent any

    stages{
        stage("Static code analysis"){
            agent {
                docker
                {
                    image 'openjdk:11'
                }
            }
            steps{
                withSonarQubeEnv(credentialsId: 'tokenforsonar') {
                    sh 'chmod +x gradlew'
                    sh './gradlew sonarqube'
                }
            }
           
        }
    }
}