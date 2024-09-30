pipeline {
    agent any

     tools {
        // Define SonarQube Scanner tool
        sonarScanner 'SonarQubeScanner'
    }

    stages {  
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
            }
        }

        stage('SonarQube Analysis') {
            steps {
                dir('dds-deploy') {
                    withSonarQubeEnv('sonarqube') { 
                        sh '''
                            sonar-scanner \
                                -Dsonar.projectKey=dds-deploy \
                                -Dsonar.sources=. \
                                -Dsonar.language=java \
                                -Dsonar.sourceEncoding=UTF-8 \
                                -Dsonar.host.url=http://sonarqube:9000 \
                                -Dsonar.login=your-sonarqube-token
                        '''
                    }
                }
            }
        }

        stage('Build') {
            steps {
               echo "Etapa Build no esta disponible"
                }
            }
        }

        stage('Test') {
            steps {
                echo "Etapa Test no esta disponible"
                //dir('dds-deploy') {
                    //echo "Ejecutando pruebas..."
                    // Ejecuta todas las pruebas o especifica el archivo de prueba
                   // sh "mvn test -Dtest=AppLibrosTest"  
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Implementar en un futuro el deploy"
                // dir('dds-deploy') {
                //     sh "docker compose down -v"
                //     sh "docker compose up -d --build"
                // }
            }
        }
    }
}
