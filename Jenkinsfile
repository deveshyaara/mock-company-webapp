pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
             steps {
                 script {
                     sh '''
                         curl -sL https://deb.nodesource.com/setup_16.x | bash -
                         apt-get update
                         apt-get install -y nodejs npm
                         npm install -g yarn
                     '''
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
