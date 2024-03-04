pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                try {
                    build 'PES1UG21CS355-1'
                } catch (err) {
                    echo "Error during custom build step: ${err.message}"
                    // Add appropriate error handling logic (e.g., notify, retry)
                }
                try {
                    sh 'g++ hello2.cpp -o output'
                } catch (err) {
                    echo "Error during COMPILE step: ${err.message}"
                    // Add appropriate error handling logic (e.g., notify, retry)
                }
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed!'
        }
    }
}
