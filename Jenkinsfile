pipeline {
  agent any
  stages {
    stage('jenkinsfile') {
      steps {
        sh 'echo $WORKSPACE'
      }
    }

    stage('build') {
      steps {
        sh '''cd my-app
mvn clean compile'''
      }
    }

    stage('test') {
      steps {
        sh '''cd my-app
mvn clean install'''
      }
    }

    stage('test-archive') {
      steps {
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
}