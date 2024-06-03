pipeline {
    agent {
        docker {
            image 'docker:19.03.12' // Use appropriate Docker image version
            args '--privileged -v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
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

