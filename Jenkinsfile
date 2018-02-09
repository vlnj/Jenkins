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
        archiveArtifacts 'C:/Users/lnvithanage/.jenkins/workspace/Jenkins_master-5WKQ4BTGQNLTBDVPBKPKFG5WYDM2XY5LI5THOPHXAJJFFZAAWTIA/Commons/target/*.jar'
      }
    }
  }
}