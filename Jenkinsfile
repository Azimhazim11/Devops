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
                sh "python3 -m venv .venv"
                sh "python3 testfile.py | docker compose up -d | pip install pytest selenium | source .venv/bin/activate"
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
