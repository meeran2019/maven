pipeline {
  agent any
  stages {
    stage('jenkinsfile') {
      steps {
        dir(path: 'my-app')
      }
    }

    stage('build') {
      steps {
        sh 'mvn clean install'
      }
    }

  }
}