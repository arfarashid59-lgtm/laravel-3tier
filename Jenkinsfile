pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Laravel App') {
            steps {
                sh 'docker build -t laravel-app:v1 .'
            }
        }

        stage('Build Nginx') {
            steps {
                sh 'docker build -t laravel-web:v1 -f docker/nginx/Dockerfile .'
            }
        }

        stage('Success') {
            steps {
                echo 'Laravel three-tier application built successfully!'
            }
        }
    }
}
