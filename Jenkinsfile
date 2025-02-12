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

    stage('package') {
      agent {
        node {
          label 'test'
        }

      }
      steps {
        sh './mvnw package -DskipTests=true'
      }
    }

  }
}