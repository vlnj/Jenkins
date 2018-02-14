pipeline {
  agent any
  stages {
    stage('Initialize') {
      parallel {
        stage('Checkout') {
          steps {
            git 'https://github.com/vlnj/Jenkins.git'
          }
        }
        stage('Pre clean') {
          steps {
            bat 'mvn clean'
          }
        }
      }
    }
    stage('Build') {
      steps {
        bat 'mvn clean install'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing ...'
      }
    }
    stage('Deploy') {
      steps {
        archiveArtifacts 'Commons/target/*.jar'
      }
    }
  }
}
