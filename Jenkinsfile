pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello ${my_name}!'
        sh 'java -version'
      }
    }
  }
}