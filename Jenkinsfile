pipeline {
    agent any

    tools {
        jdkJDK17'
    }

    stages {
        stage('Clean Workspace') {
            steps {
                echo 'Cleaning workspace before build...'
                cleanWs()
            }
        }

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                \
            }
        }

        stage('Compile Java') {
            steps {
                echo 'Compiling HelloWorld.java...'
                
                bat 'javac HelloWorld.java'
            }
        }

        stage('Archive Artifacts') {
            steps {
                echo 'Archiving compiled class files...'
                
                archiveArtifacts artifacts: '*.class', fingerprint: true
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished. Cleaning up...'
        }
        success {
            echo ' SUCCESS: The pipeline completed successfully!'
        }
        failure {
            echo ' FAILURE: The pipeline failed. Check the logs for details.'
        }
        unstable {
            echo ' UNSTABLE: The pipeline is unstable (e.g., test failures).'
        }
        changed {
            echo ' Status changed from the previous build.'
        }
    }
}