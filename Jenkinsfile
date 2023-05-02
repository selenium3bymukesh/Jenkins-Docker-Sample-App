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
            docker build -t pythonapp:latest .
            '''
          },
          test: {
            echo "This is dummy step"
          }
        )
      }
    }
    stage('Approval') {
      steps {
        input('Do you want to Deploy?')
      }
    }
    stage('Deploy') {
      steps{
        sh'docker run -d -p 80:5000 --name pythonapp pythonapp:latest'
      }
    }
  }
}
