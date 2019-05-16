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
ls -lah
whoami'''
          }
        }
        stage('Requirement') {
          steps {
            withEnv(overrides: ["HOME=${env.WORKSPACE}"]) {
              sh '''python --version
pip install pylint --user'''
            }

          }
        }
      }
    }
    stage('Static Code Scan') {
      steps {
        echo 'PEP-8 Style Check'
        sh '/usr/bin/pylint --disable=C command.py'
      }
    }
  }
}