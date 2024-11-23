pipeline {
    agent any  // This means the pipeline can run on any available agent.

    stages {
        stage('Build') {
            steps {
                // Your build command here (e.g., Gradle or Maven build)
                script {
                    sh './gradlew assemble'
                }
            }
        }

        stage('Test') {
            steps {
                // Your test command here (e.g., running unit tests)
                script {
                    sh './gradlew test'
                }
            }
        }

        // Add more stages as needed (e.g., Deploy)
    }
}
