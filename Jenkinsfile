pipeline {
    agent any

    environment {
        PYTHONUNBUFFERED = '1'
    }

    stages {
        stage('Checkout') {
            steps {
                // Jenkins automatically checks out the code, but you can make it explicit
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    python3 -m venv venv
                    source venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run App') {
            steps {
                sh '''
                    source venv/bin/activate
                    nohup python app.py > output.log 2>&1 &
                '''
            }
        }
    }
}
