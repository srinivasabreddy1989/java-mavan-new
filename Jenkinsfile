pipeline {
    agent {
        docker {
            image 'maven:3.9.11-eclipse-temurin-21'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh 'mvn -version'
            }
        }
    }
}