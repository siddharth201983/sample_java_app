@Library("my-shared-library") _

pipeline {
    agent any

    stages {
        stage("Clean Workspace"){
            steps{
                cleanWs()
            }
        }
        stage("Git Checkout"){
            steps{
                git branch: 'main', credentialsId: 'gitcred', url: 'https://github.com/siddharth201983/sample_java_app.git'
            }
        }
        stage("Test Application"){
            steps{
                sh 'mvn test'
            }
        }
        stage("Integration Test maven"){
            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }
        stage("SonarQube Analysis"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonaqube-api') {
                        sh 'mvn clean package sonar:sonar'
                }
              }
            }
        }
    }
}
