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
        stage('error') {
          steps {
            readFile(file: 'C:\\User\\.jenkins\\workspace\\Jenkins_master-5WKQ4BTGQNLTBDVPBKPKFG5WYDM2XY5LI5THOPHXAJJFFZAAWTIA\\pom.xml', encoding: 'utf-8')
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