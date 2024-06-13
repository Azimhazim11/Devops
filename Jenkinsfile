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
                sh "python3 testfile.py | docker compose up -d | source .venv/bin/activate | pip install pytest selenium"
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
