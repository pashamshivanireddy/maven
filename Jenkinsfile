pipeline {
    agent any

    tools {
        maven '3.9.11'     // Must match Jenkins config
        jdk 'java 21'       // Must match Jenkins config
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        failure {
            echo 'Build or tests failed.'
        }
        success {
            echo 'Build and tests succeeded.'
        }
    }
}
