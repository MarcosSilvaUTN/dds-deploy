Pipeline{
  agent any

  stages{
      stage('Build'){
          steps{
              echo "Estapa Build no disponible"
          }

      stage('Test'){
          steps{
              echo "Estapa Test no disponible"
          }
      } 
        
      stage('Deploy'){
          steps{
              sh "docker compose down -v"
              sh "docker compose up -d --build"
          }
  }
}
