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
      steps {
        sh './mvnw package -DskipTests=true'
      }
    }

    stage('int test') {
      agent {
        node {
          label 'test'
        }

      }
      steps {
        node(label: 'test') {
          sh './mvnw verify -P tomcat90'
        }

      }
    }

  }
}