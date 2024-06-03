pipeline {
    agent any

    stages {
        stage('build Docker Image') {
            steps {
                withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker', url: '0scar996') {
                    sh "docker build -t oscar/frontend:latest ."
                }
            }
        }
        
        stage('push Docker Image') {
            steps {
                withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker', url: '0scar996') {
                    sh "docker push oscar/frontend:latest"
                }
            }
        }
    }
}
