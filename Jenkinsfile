pipeline {
  agent {
    docker {
      image 'python:3.5.1'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build Stage'
          }
        }
        stage('Requirement') {
          steps {
            script {
              sh 'python --version'
            }

          }
        }
      }
    }
  }
}