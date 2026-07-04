pipeline {
    agent {
        docker {
            image 'maven:3.9.11-eclipse-temurin-21'
            args '''
                -e HOME=/root
                -v /var/lib/jenkins/.m2:/root/.m2
            '''
        }
    }

    stages {
        stage('Debug') {
    steps {
        sh '''
            id
            whoami || true
            echo "HOME=$HOME"
            pwd
            ls -ld /root || true
            ls -ld /root/.m2 || true
            ls -ld /var/lib/jenkins || true
        '''
        }
    }

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