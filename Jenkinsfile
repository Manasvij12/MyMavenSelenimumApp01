pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Manasvij12/MyMavenSelenium.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Run Selenium') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="App"'
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
