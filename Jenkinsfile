pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        sh 'mvn checkout'
      }
    }
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'dev'
          }
        }
        stage('dev') {
          steps {
            sh 'compile'
          }
        }
        stage('QA') {
          steps {
            sh 'package'
          }
        }
      }
    }
    stage('test') {
      steps {
        sh 'testing'
      }
    }
    stage('deploy') {
      steps {
        sh 'mvn deploy'
      }
    }
  }
}