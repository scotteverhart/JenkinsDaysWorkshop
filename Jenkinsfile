pipeline {
  agent {
    label 'jdk9'
  }
  stages {
  stage('Testing') {
        parallel {
          stage('Java 9') {
            agent { label 'jdk9' }
            steps {
              container('maven9') {
                sh 'mvn -v'
              }
            }
          }
          stage('Java 8') {
            agent { label 'jdk8' }
            steps {
              container('maven8') {
                sh 'mvn -v'
              }
            }
          }
        }
      }
  }
  environment {
    MY_NAME = 'NoneYa'
    TEST_USER = credentials('test-user')
  }
  post {
    aborted {
      echo 'Why didn\'t you push my button?'

    }

  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
