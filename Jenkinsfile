pipeline {
  agent any
  stages {
    stage('Hello') {
      steps {
        sh '''
           #!/bin/bash
           echo "Hello World"
           '''
      }
    }
    stage('Building App') {
      steps{
        sh '''
           docker build -t pythonapp .
           '''
      }
    }
  }
}
