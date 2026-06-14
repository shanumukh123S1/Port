pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Downloading Code'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t portfolio .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f portfolio-container || true'
                sh 'docker run -d --name portfolio-container -p 80:80 portfolio'
            }
        }
    }
}
