pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git branch: 'master' , url: 'https://github.com/SAKETHVUNKA/PES1UG21CS355_Jenkins.git'
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG21CS355-1'
                sh 'g++ main.cpp -o output'
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
