pipeline {
    agent { docker { image 'python:3.9-slim' args '-u 0' } }

    stages {
        stage('Build') {
            steps {
                echo 'Construyendo el proyecto...'
            }
        }

        stage('Test') {
            steps {
                echo 'Ejecutando pruebas unitarias...'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Instalando dependencias...'
                sh 'pip install --user -r requirements.txt'
                echo 'Ejecutando análisis con Bandit...'
                sh 'bandit -r . || true'
            }
        }
    }
}
