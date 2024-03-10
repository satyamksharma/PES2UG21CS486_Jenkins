pipeline {

  agent any

  stages {
    stage('Clone repository') {
      steps {
        checkout([$class: 'GitSCM',
          //branches: [[name: '*/main']],  // Commented out if not specifying branch
          userRemoteConfigs: [[url: 'https://github.com/satyamksharma/PES2UG21CS486_Jenkins.git']]])
      }
    }
    stage('Build') {
      steps {
        build 'PES2UG21CS486-1'
        sh 'g++ main.cpp -o output' // Add shell script to compile .cpp file (use 'sh' for Unix-based systems, 'bat' for Windows)
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
