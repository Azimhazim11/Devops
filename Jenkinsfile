pipeline {
 agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh "docker compose build"
                sh "docker compose down"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh "python3 -m venv .venv"
                sh "docker compose up -d"
                sh "source .venv/bin/activate && pip install pytest selenium && python3 testfile.py"
                // sh "source .venv/bin/activate"
                // sh "pip install pytest selenium"
                // sh "docker compose up -d"
                // sh "python3 testfile.py"
            
            }
        }
        stage('Deploy') {
            steps {
                sh "git"
                echo 'Deploying....'
            }
        }
    }
}
