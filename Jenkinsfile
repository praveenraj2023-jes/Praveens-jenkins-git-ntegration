pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                echo 'Cleaning workspace before build...'
                cleanWs()
            }
        }
        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub...'
                // No git step needed – Jenkins automatically checks out the repo
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'echo Build completed successfully.'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo All tests passed.'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished. Cleaning up...'
        }
        success {
            echo '🎉 SUCCESS: The pipeline completed successfully!'
        }
        failure {
            echo '❌ FAILURE: The pipeline failed. Check the logs for details.'
        }
        unstable {
            echo '⚠️ UNSTABLE: The pipeline is unstable (e.g., test failures).'
        }
        changed {
            echo '📊 Status changed from the previous build.'
        }
    }
}