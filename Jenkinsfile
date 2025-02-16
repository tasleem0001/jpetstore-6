pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hi, first step'
        sh './mvnw clean compile'
      }
    }

    stage('Unit Test') {
      steps {
        sh './mvnw test'
      }
    }

  }
}