pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/farisRajendra/test-jenkins.git'
            }
        }

        stage('Install PHP dependencies') {
            steps {
                sh 'composer install'
            }
        }

        stage('Install Node dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Frontend') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Run Laravel Test') {
            steps {
                sh 'php artisan test'
            }
        }
    }
}
