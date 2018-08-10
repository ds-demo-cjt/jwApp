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
    stage('Approvals') {
      steps {
        input(message: 'Approve Deployment', id: 'deploy')
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deployment'
      }
    }
  }
}