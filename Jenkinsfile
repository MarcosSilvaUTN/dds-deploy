pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                sh "https://github.com/MarcosSilvaUTN/dds-deploy.git"
            }
        }

        stage('Build') {
            steps {
                echo "Etapa Build no disponible"
            }
        }

        stage('Test') {
            steps {
                echo "Etapa Test no disponible"
            }
        }

        stage('Deploy') {
            steps {
                sh "docker compose down -v"
                sh "docker compose up -d --build"
            }
        }
    }
}
