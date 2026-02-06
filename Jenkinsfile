pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Code checked out"
                sh "ls"
            }
        }

        stage('Setup Python') {
            steps {
                sh """
                python --version
                python -m venv venv
                . venv/bin/activate
                pip install -r requirements.txt
                """
            }
        }

        stage('Run Tests') {
            steps {
                sh """
                . venv/bin/activate
                python -c "import main; print('App import success')"
                """
            }
        }
    }
}
