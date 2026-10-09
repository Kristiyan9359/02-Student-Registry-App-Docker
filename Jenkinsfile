
pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t kristiyan9359/student-registry:latest .'
            }
        }

        stage('Push Docker Image') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-credentials',
                    usernameVariable: 'DOCKER_USERNAME',
                    passwordVariable: 'DOCKER_PASSWORD'
                )]) {
                    bat 'docker login -u "%DOCKER_USERNAME%" -p "%DOCKER_PASSWORD%"'
                    bat 'docker push kristiyan9359/student-registry:latest'
                }
            }
        }
    }
}
stage('Trigger CD') {
    steps {
        build job: 'StudentRegistry-CD',
              wait: false
    }
}
