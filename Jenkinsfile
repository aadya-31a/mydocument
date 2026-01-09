pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'echo "Building application"'
            sh '''echo "Building application"
mvn clean package'''
          }
        }

        stage('error') {
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
            sh '''echo "Running tests"
mvn test'''
          }
        }

        stage('error') {
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
            sh '''echo "Deploying application"
java -jar target/myapp.jar '''
          }
        }

        stage('error') {
          steps {
            sh 'java -jar target/myapp.jar'
          }
        }

      }
    }

  }
}