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
      parallel {
        stage('test') {
          steps {
            sh '''cd my-app
mvn clean install'''
          }
        }

        stage('stash-stage') {
          steps {
            stash(name: 'stash-file', allowEmpty: true)
          }
        }

      }
    }

    stage('test-archive') {
      steps {
        archiveArtifacts '**/target/*.jar'
      }
    }

    stage('unstash') {
      steps {
        unstash 'stash-file'
      }
    }

  }
}