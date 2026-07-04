pipeline {
    agent {
        docker {
            image 'maven:3.9.11-eclipse-temurin-21'
            args '-v /var/lib/jenkins/.m2:/root/.m2'
        }
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }
}