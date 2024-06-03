pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
                    sh "docker build -t oscar/frontend:latest ."
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                withDockerRegistry(credentialsId: 'docker-cred', url: 'https://index.docker.io/v1/') {
                    sh "docker push oscar/frontend:latest"
                }
            }
        }
    }
}

        
