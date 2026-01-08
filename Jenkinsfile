pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "Building application"'
          }
        }

        stage('') {
          steps {
            sh 'mvn clean compile package'
            sh 'mvn clean compile package'
          }
        }

      }
    }

    stage('Test') {
      steps {
        sh 'echo "Running tests"'
      }
    }

    stage('Deploy') {
      steps {
        sh 'echo "Deploying application"'
      }
    }

  }
}