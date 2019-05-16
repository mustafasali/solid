pipeline {
  agent {
    docker {
      image 'python:3.5.1'
    }

  }
  stages {
    stage('Build') {
      parallel {
        stage('Checkpoint') {
          steps {
            echo 'Build Stage'
            sh 'date'
          }
        }
        stage('Requirement') {
          steps {
            sh 'python --version'
          }
        }
      }
    }
  }
}