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
          }
        }

      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'echo "Running tests"'
          }
        }

        stage('') {
          steps {
            sh 'mvn test'
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            sh 'echo "Deploying application"'
          }
        }

        stage('') {
          steps {
            sh 'java -jar target/myapp.jar'
          }
        }

      }
    }

  }
}