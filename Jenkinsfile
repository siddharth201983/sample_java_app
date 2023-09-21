pipeline {
    agent any

    stages {
        stage("Git Checkout"){
            steps{
                script{
                    git branch: 'main', credentialsId: 'gitcred', url: 'https://github.com/siddharth201983/sample_java_app.git'
                }
            }
        }
    }
}
