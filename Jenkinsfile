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
        stage("Build Application"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Test Application"){
            steps{
                sh 'mvn test'
            }
        }
        stage("SonarQube Analysis"){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonaqube-api') {
                        sh 'mvn sonar:sonar'
                }
              }
            }
        }
    }
}
