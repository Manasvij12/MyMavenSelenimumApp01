pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Run Selenium') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }

    post {
        success {
            echo 'Maven Selenium execution successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
