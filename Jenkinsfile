pipeline {
    agent any  // Specifies that the pipeline will run on any available agent

    environment {
        // Define any environment variables needed, if necessary
        GRADLE_HOME = '/usr/local/gradle'  // Example if you have a specific Gradle installation, adjust as necessary
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Run the 'assemble' task to build and package the application
                script {
                    sh './gradlew assemble'  // For Linux/MacOS, use './gradlew assemble'
                    // On Windows, you can use 'gradlew assemble' directly
                }
            }
        }

        stage('Test') {
            steps {
                // Run unit tests
                script {
                    sh './gradlew test'  // For Linux/MacOS, use './gradlew test'
                    // On Windows, you can use 'gradlew test' directly
                }
            }
        }

        stage('Build and Package') {
            steps {
                // Run 'build' to ensure tests pass and the package is generated
                script {
                    sh './gradlew build'  // For Linux/MacOS, use './gradlew build'
                    // On Windows, use 'gradlew build' directly
                }
            }
        }

        stage('Run Application') {
            steps {
                // Run the application using the 'bootRun' task
                script {
                    sh './gradlew bootRun'  // For Linux/MacOS, use './gradlew bootRun'
                    // On Windows, use 'gradlew bootRun' directly
                }
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps here if needed
                echo 'Deploy stage - Add deployment steps as per your requirements.'
            }
        }
    }

    post {
        success {
            // Any post-success actions (such as sending notifications)
            echo 'Build and tests were successful.'
        }
        failure {
            // Any post-failure actions (such as sending failure notifications)
            echo 'Build or tests failed.'
        }
    }
}
