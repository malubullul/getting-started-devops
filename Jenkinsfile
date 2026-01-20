pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t getting-started-app:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop getting-started || true
                docker rm getting-started || true
                docker run -d -p 8081:80 --name getting-started getting-started-app:latest
                '''
            }
        }
    }
}
