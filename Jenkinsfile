pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Client Tests') {
      steps {
        dir(path: 'docker-react') {
          sh 'npm install'
          sh 'npm test'
        }

      }
    }

  }
}