pipeline {
  agent any
  stages {
    stage('Initialize') {
      parallel {
        stage('Initialize') {
          steps {
            bat 'mvn clean'
          }
        }
        stage('') {
          steps {
            readFile(file: 'pom.xml', encoding: 'utf-8')
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