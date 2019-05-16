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
            sh '''date
ls -lah'''
          }
        }
        stage('Requirement') {
          steps {
            sh 'python --version'
          }
        }
      }
    }
    stage('Static Code Scan') {
      steps {
        echo 'PEP-8 Style Check'
        sh 'pylint --disable=C command.py || true'
      }
    }
  }
}