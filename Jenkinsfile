pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install --break-system-packages -r requirements.txt'
            }
        }

        stage('Build') {
            steps {
                sh 'python3 -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                sh 'pytest'
            }
        }

        stage('Package') {
            steps {
                sh 'tar -czf python-app.tar.gz app.py requirements.txt test_app.py'
            }
        }
    }
}
