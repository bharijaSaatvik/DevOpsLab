pipeline{
    agent any
    stages{
        stage("Static code analysis"){
            agent {
                docker {
                    image 'openjdk:17'
                }
            }
            steps{
                script {
                    withSonarQubeEnv('sonarserver') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                }
                }
            }
           
        }
    }
}