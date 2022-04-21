pipeline {
  agent any
  stages {
    stage('jenkinsfile') {
      parallel {
        stage('jenkinsfile') {
          steps {
            sh 'echo $WORKSPACE'
          }
        }

        stage('notification') {
          steps {
            emailext(subject: 'jenkins - build -start', body: 'build started', to: 'sheikmeeran.sj@gmail.com')
          }
        }

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

    stage('display-ws') {
      steps {
        sh '''echo $WORKSPACE
ls '''
      }
    }

    stage('confirm for deployment') {
      steps {
        input(message: 'Approve or Reject', ok: 'lets do it')
      }
    }

    stage('display value') {
      steps {
        echo 'deployed successfully'
        sh '''echo "$type"
echo "$region"'''
      }
    }

  }
  environment {
    region = 'dev'
    type = 't2-micro'
  }
  post {
    success {
      echo 'post success'
    }

    failure {
      echo 'post failure'
    }

  }
}