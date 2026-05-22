pipeline {
    agent any

    tools {
        maven 'maven3.9'
        jdk 'jdk17'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }

        stage('Test Webhook') {
            steps {
                echo 'Incroyable, le webhook fonctionne tout seul !'
            }
        }
    }
}
