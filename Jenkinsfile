pipeline {
  agent {
    docker {
      image 'maven:3.5.0-jdk-8'
    }
    
  }
  stages {
    stage('Welcome') {
      steps {
        parallel(
          "Welcome": {
            echo 'Saludo'
            
          },
          "Otener cambios": {
            git 'https://github.com/juanvillacc/sampleapp.git'
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit 'target/'
      }
    }
  }
}