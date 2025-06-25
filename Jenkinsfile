pipeline {
  agent any

  stages {
    stage('Clonar repositorio') {
      steps {
        git 'https://github.com/Iamhern4n/proyectoy.git'
      }
    }

    stage('Desplegar app en Docker en la VM') {
      steps {
        sshagent(['debian']) {
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

