pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "docker compose build"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "python3 -m venv /venv"
                sh "source /venv/bin/activate"
                sh "pip install pytest selenium"
                sh "docker compose up -d"
                sh "python testfile.py"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}