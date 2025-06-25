pipeline {
  agent any

  stages {
    stage('Desplegar app en Docker en la VM') {
      steps {
        sshagent(['debian']) {
          sh '''
            ssh -o StrictHostKeyChecking=no debian@20.63.73.106 "
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


