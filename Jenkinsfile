pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/vatitko/repo1.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run App') {
            steps {
                sh 'nohup python app.py &'
            }
        }
    }
}
