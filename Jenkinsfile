pipeline {
    agent any
    stages {
        stage('Build & Deploy Webserver') {
            steps {
                dir('.') {
                    // Build and restart the Docker container
                    sh 'docker compose up -d --build webserver'
                }
            }
        }
    }
}
