@Library("my-shared-library") _

pipeline {
    agent any

    stages {
        stage("Git Checkout"){
            steps{
                gitCheckout{
                    branch: "main",
                    url: 'https://github.com/siddharth201983/sample_java_app.git'
                }
            }
        }
    }
}
