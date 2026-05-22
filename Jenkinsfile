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
                // On compile uniquement ici
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                // On exécute les tests unitaires de l'application
                bat 'mvn test'
            }
        }
    }
}
