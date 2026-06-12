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
                bat 'docker build -t portfolio .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f portfolio-container || exit 0'
                bat 'docker run -d --name portfolio-container -p 80:80 portfolio'
            }
        }
    }
}
