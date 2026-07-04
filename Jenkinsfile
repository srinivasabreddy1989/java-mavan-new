pipeline {
    agent {
        docker {
            image 'maven:3.9.11-eclipse-temurin-21'
            args '-v /var/lib/jenkins/.m2:/home/jenkins/.m2'
        }
    }

    environment {
        MAVEN_OPTS = '-Dmaven.repo.local=/home/jenkins/.m2/repository'
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