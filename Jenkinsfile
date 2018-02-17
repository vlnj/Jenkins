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
          }
        }
        stage('Safari') {
          steps {
            echo 'Testing Safari'
          }
        }
        stage('Explorer') {
          steps {
            echo 'testing explorer'
          }
        }
      }
    }
    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            archiveArtifacts 'Commons/target/*.jar'
          }
        }
        stage('') {
          steps {
            svn 'svn://YOURCOMPUTERNAME/repository/project/trunk'
          }
        }
      }
    }
  }
}