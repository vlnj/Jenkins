pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        bat 'mvn clean'
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