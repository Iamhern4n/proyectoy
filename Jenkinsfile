pipeline {
  agent any

  stages {
    stage('Desplegar app en Docker en la VM') {
      steps {
        sshagent(['mi-clave-ssh']) {
          sh '''
            ssh -o StrictHostKeyChecking=no debian@localhost "
              cd proyectoy &&
              git pull &&
              docker-compose down &&
              docker-compose up -d --build
            "
          '''
        }
      }
    }
  }
}


