pipeline {
  agent any
  stages {
    stage('error') {
      agent {
        node {
          label 'worker'
        }

      }
      steps {
        echo 'hi'
      }
    }

  }
}