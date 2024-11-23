pipeline {
    agent any  // Specifies that the pipeline will run on any available agent

    stages {
        stage('Build') {
            steps {
                // Build step (replace with actual build commands)
                script {
                    sh './gradlew assemble'
                }
            }
        }

        stage('Test') {
            steps {
                // Test step (replace with actual test commands)
                script {
                    sh './gradlew test'
                }
            }
        }

        // You can add more stages like 'Deploy', 'Lint', etc. as needed
    }
}
