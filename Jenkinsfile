pipeline {
  agent { label 'aws-agent' }

  stages {
    stage('Check Agent') {
      steps {
        sh 'hostname'
        sh 'echo TMPDIR is: $TMPDIR'
        sh 'df -h'
      }
    }
  }
}
