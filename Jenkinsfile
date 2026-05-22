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
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                // Étape 1 : On package l'application en ignorant les tests (puisqu'ils viennent d'être faits avant)
                bat 'mvn package -DskipTests'
                
                // Étape 2 : On dit à Jenkins de sauvegarder le fichier JAR généré
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}
