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
        node(label: 'test') {
          sh './mvnw package -DskipTests=true'
        }

      }
    }

    stage('deploy') {
      steps {
        node(label: 'test') {
          sh './mvnw cargo:run -P tomcat90'
        }

      }
    }

  }
}