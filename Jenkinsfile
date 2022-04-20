pipeline {
  agent none
  stages {
    stage('jenkinsfile') {
      agent any
      steps {
        sh 'echo $WORKSPACE'
      }
    }

    stage('build') {
      agent any
      steps {
        sh '''cd my-app
mvn clean compile'''
      }
    }

    stage('test') {
      agent any
      steps {
        sh '''cd my-app
mvn clean install'''
      }
    }

    stage('test-archive') {
      agent any
      steps {
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
}