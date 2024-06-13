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
                // sh "python3 testfile.py | docker compose up -d | pip install pytest selenium | source .venv/bin/activate"
                sh "source .venv/bin/activate"
                sh "pip install pytest selenium"
                sh "docker compose up -d"
                sh "python3 testfile.py"
            
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
