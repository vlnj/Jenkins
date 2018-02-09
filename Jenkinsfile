pipeline {
  agent any
  stages {
    stage('Initialize') {
      steps {
        bat(script: 'C:\\Work\\batch\\init.bat', encoding: 'utf-8', returnStdout: true)
      }
    }
    stage('Build') {
      steps {
        bat(script: 'C:\\Work\\batch\\build.bat', encoding: 'utf-8', returnStdout: true)
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