pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Install Node.js and npm using sudo
                    sh 'sudo curl -sL https://deb.nodesource.com/setup_16.x | bash -'
                    sh 'sudo apt-get install -y nodejs'
                    sh 'sudo npm install -g yarn'
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
