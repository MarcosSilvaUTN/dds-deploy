pipeline {
    agent any

    stage('Repositorio') {
    steps {
        script {
            if (fileExists('dds-deploy')) {
                dir('dds-deploy') {
                    sh "git pull origin main"  // Actualiza el repositorio
                }
            } else {
                sh "git clone https://github.com/MarcosSilvaUTN/dds-deploy.git" // Clona el repositorio si no existe
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
                echo "Implementar en un futuro el deploy"
                // dir('dds-deploy') {
                   // sh "docker compose down -v"
                   // sh "docker compose up -d --build"
                }
            }
        }
    }
}
