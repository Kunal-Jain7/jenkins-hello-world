pipeline {
    agent any

    tools {
        maven 'M398'
    }

    stages {
        stage('Test Version') {
            steps {
                sh 'echo Testing the Maven version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                // Building the code
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Unit tests') {
            steps {
                sh 'mvn test'
            }
        }
    }
}