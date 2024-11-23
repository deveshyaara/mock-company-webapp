pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Install npm and yarn if they are not installed
                    sh 'curl -sL https://deb.nodesource.com/setup_16.x | bash -'  // Install Node.js
                    sh 'apt-get install -y nodejs'  // Install Node.js and npm
                    sh 'npm install -g yarn'  // Install Yarn
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh './gradlew assemble'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './gradlew test'
                }
            }
        }
    }
}
