pipeline {
    agent any

    tools {
        jdk 'JDK11'
        maven 'Maven3'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Yuvanya-Jayasankar/SeleniumDemo.git'
            }
        }

        stage('Build Project') {
            steps {
                echo 'Building project using Maven'
                bat 'mvn clean compile'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                echo 'Running Selenium tests'
                bat 'mvn test'
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed'
        }
        success {
            echo 'Build & Tests successful'
        }
        failure {
            echo 'Build or Tests failed'
        }
    }
}