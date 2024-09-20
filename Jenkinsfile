pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git branch: 'main', url: 'https://github.com/MichaelCaukill/Apply4A.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-nginx .'
            }
        }
        stage('Deploy to Docker Swarm') {
            steps {
                sh 'docker stack deploy -c docker-compose.yml nginx'
            }
        }
    }
}
