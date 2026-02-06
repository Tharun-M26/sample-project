pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code is already checked out from GitHub'
                sh 'ls'
            }
        }

        stage('Build') {
            steps {
                echo 'Simulating build step'
                sh 'echo Building project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Simulating test step'
                sh 'echo Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Simulating deployment step'
                sh 'echo Deploying application...'
            }
        }
    }
}
