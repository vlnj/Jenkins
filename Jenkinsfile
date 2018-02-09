pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        sh '''echo PATH = %PATH%
echo M2_HOME = %M2_HOME%
mvn clean'''
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing ...'
      }
    }
    stage('Deploy') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }
  }
}