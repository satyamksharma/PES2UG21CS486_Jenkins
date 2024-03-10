pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        build 'PES2UG21CS486-1'
        sh 'g++ working.cpp -o output' // Add shell script to compile .cpp file (use 'sh' for Unix-based systems, 'bat' for Windows)
      }
    }
    stage('Test') {
      steps {
        sh './output' // Add shell script to test .cpp file
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy' // Add shell script for deployment if needed
      }
    }
  }

  post {
    failure {
      error 'Pipeline failed'
    }
  }
}
