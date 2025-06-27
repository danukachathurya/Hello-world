pipeline {

    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('clean') {
            steps {
                sh "mvn clean"
            }
        }

        stage('install') {
            steps {
                sh "mvn install -DskipTests"
            }
        }

        stage('package') {
            steps {
                sh "mvn package -DskipTests"
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    sh "sudo docker build -t java-test-app:latest ."
                }
            }
        }

    }
}
