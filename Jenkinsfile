pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh '''./jenkins/scripts/test.sh
echo \'Test success\''''
      }
    }
    stage('Deliver') {
      steps {
        sh '''./jenkins/scripts/deliver.sh
echo \'Deliver success\''''
      }
    }
  }
  environment {
    CI = 'True'
  }
}