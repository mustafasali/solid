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
who -u'''
          }
        }
        stage('Setup Virtualenv') {
          steps {
            sh '''sudo pip install virtualenv
mkdir -p ~/.virtualenvs
virtualenv ~/.virtualenvs/pylint
. ~/.virtualenv/pylint/bin/activate'''
          }
        }
        stage('Install Packages') {
          steps {
            sh '''python --version
pip install pylint --user'''
          }
        }
      }
    }
    stage('Static Code Scan') {
      steps {
        echo 'PEP-8 Style Check'
        sh '''

pylint --disable=C command.py'''
      }
    }
  }
}