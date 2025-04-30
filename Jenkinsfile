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
                sh 'rm -rf node_modules'
                sh 'rm -rf package-lock.json'
                sh 'npm install'
            }
        }
        stage('Build Frontend') {
            steps {
                sh 'chmod +x ./node_modules/.bin/vite'
                sh 'node ./node_modules/vite/bin/vite.js build'
            }
        }
        stage('Run Laravel Test') {
            steps {
                sh 'php artisan test'
            }
        }
    }
}