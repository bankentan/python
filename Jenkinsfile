pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'ok'
        input(message: 'please input', id: 'you key', ok: 'go', submitter: 'bankentan', submitterParameter: 'yongjia')
      }
    }
  }
}