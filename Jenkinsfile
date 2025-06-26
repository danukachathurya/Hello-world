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

        // stage('Build Docker Image with Kaniko') {
        //     steps {
        //         container('kaniko') {
        //             script {

        //                 // Run Kaniko Build Command
        //                 sh "pwd"
        //                 sh "ls -a"
        //                 sh "/kaniko/executor --dockerfile `pwd`/Dockerfile --context `pwd` --destination=azdevopscourse.azurecr.io/sample-java-project:latest" 
        //             }
        //         }
        //     }
        // }

    }
}
