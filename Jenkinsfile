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
mvn clean install'''
      }
    }

  }
}