pipeline {
  agent { label 'aws-agent' }

  environment {
    IMAGE_NAME = "java-app"
    TAG = "latest"
  }

  stages {
    stage('Build JAR') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t $IMAGE_NAME:$TAG .'
      }
    }

    stage('List Docker Images') {
      steps {
        sh 'docker images'
      }
    }
  }
}
