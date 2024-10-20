pipeline{
    agent any
    stages{
        stage("Static code analysis"){
            // agent {
            //     docker {
            //         image 'openjdk:17'
            //     }
            // }
            steps{
                script {
                    docker.image('openjdk:17').inside('/c/ProgramData/Jenkins/.jenkins/workspace/java-application@2/')
                    withSonarQubeEnv('sonarserver') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                }
                }
            }
           
        }
    }
}