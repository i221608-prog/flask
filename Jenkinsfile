pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Check Python') {
            steps {
                sh '''
                python3 --version
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                pip3 install -r requirements.txt || true
                '''
            }
        }

        stage('Test App') {
            steps {
                sh '''
                python3 -m py_compile app.py
                echo "Flask app syntax OK"
                '''
            }
        }
    }
}
