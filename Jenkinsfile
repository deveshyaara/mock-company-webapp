pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // TODO: Checkout the repository code
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // TODO: Add Gradle build command
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                // TODO: Add Gradle test command
                sh './gradlew test'
            }
        }
    }

    post {
        always {
            // Always archive build and test results, if available
            archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
            junit '**/build/test-results/**/*.xml'
        }
    }
}
