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
                archiveArtifacts artifacts: 'target/hello-demo-*.jar'
            }
        }
        stage('Unit tests') {
            steps {
                sh 'mvn test'
                junit keepProperties: true, keepTestNames: true, testResults: 'target/surefire-reports/TEST-*.xml'
            }
        }
    }
}