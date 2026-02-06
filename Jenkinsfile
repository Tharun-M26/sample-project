pipeline {
    agent any

    environment {
        IMAGE_NAME = "tharun2604/sample-project"
        CONTAINER_NAME = "sample-app"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Code already checked out"
                sh "ls"
            }
        }

        stage('Setup Python') {
            steps {
                sh """
                python --version
                python -m venv venv
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt
                """
            }
        }

        stage('Run Tests') {
            steps {
                sh """
                . venv/bin/activate
                pytest || true
                """
            }
        }

        stage('Build Docker Image') {
            steps {
                sh """
                docker build -t $IMAGE_NAME .
                """
            }
        }

        stage('Run Docker Container') {
            steps {
                sh """
                docker rm -f $CONTAINER_NAME || true
                docker run -d -p 8000:8000 --name $CONTAINER_NAME $IMAGE_NAME
                """
            }
        }
    }
}
