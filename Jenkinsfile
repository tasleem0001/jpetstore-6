pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hello'
        sh './mvnw clean compile'
      }
    }

    stage('Test') {
      steps {
        sh './mvnw test'
      }
    }

  }
}