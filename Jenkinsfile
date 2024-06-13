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
                sh "source .venv/bin/activate | pip install pytest selenium | docker compose up -d | python3 testfile.py"
                
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
