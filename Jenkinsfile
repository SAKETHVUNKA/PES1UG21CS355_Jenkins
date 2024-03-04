pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES1UG21CS355-1'
                sh 'g++ hello2.cpp -o output'
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
