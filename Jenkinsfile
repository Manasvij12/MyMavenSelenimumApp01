pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run Selenium') {
            steps {
                sh 'java -jar target/MyMavenSeleniumApp01-1.0-SNAPSHOT.jar'
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
