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
mvn clean build'''
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('test-archive') {
      steps {
        archiveArtifacts '*.jar'
      }
    }

  }
}