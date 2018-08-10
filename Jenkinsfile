pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hello JenkinsWorld'
        sh 'java -version'
      }
    }
    stage('Test') {
      failFast true
      parallel {
        stage('Test') {
          agent any
          steps {
            sh 'java -version'
            sleep 20
          }
        }
        stage('Java9') {
          steps {
            sh 'java -version'
            sleep 20
          }
        }
      }
    }
  }
}