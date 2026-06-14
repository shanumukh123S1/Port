pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t portfolio .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f portfolio-container || true'
                sh 'docker run -d --restart unless-stopped --name portfolio-container -p 80:80 portfolio'
            }
        }
    }
}
