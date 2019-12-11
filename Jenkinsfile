pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'echo "building"'
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh 'echo "Test stage, and the env CI value : $CI"'
      }
    }

    stage('Deliver ') {
      steps {
        sh 'echo "Deliver"'
        input(message: 'Finished using the web site? (Click "Proceed" to continue)', id: 'inputValue', ok: 'Process')
        sh 'echo "kill"'
      }
    }

  }
}