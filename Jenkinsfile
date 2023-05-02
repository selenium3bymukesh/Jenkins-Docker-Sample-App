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
        parallel(
          build: {
            sh '''
            docker build -t pythonapp .
            '''
          },
          test: {
            echo "This is dummy step"
          }
        )
      }
    }
  }
}
