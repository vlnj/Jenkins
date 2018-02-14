pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/vlnj/Jenkins.git'
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage('Test') {
      parallel {
        stage('Firefox') {
          steps {
            echo 'Testing Firefox'
          }
        }
        stage('Chrome') {
          steps {
            echo 'Testing Chrome'
            def response = httpRequest "http://localhost:6029/configar-api/test"
            echo response.content
            
          }
        }
        stage('Safari') {
          steps {
            echo 'Testing Safari'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        archiveArtifacts 'Commons/target/*.jar'
      }
    }
  }
}
