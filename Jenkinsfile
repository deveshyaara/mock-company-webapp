pipeline {
    agent any  // This tells Jenkins to run the pipeline on any available agent.

    stages {
        stage('Build') {
            steps {
                // Build step (replace this with your actual build command)
                script {
                    sh './gradlew assemble'
                }
            }
        }

        stage('Test') {
            steps {
                // Test step (replace this with your actual test command)
                script {
                    sh './gradlew test'
                }
            }
        }

        // Add more stages as needed (e.g., Deploy)
    }
}
