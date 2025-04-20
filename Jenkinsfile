pipeline {
  agent { label 'aws-agent' }

  environment {
    IMAGE_NAME = "java-app"
    TAG = "latest"
    AWS_REGION = "us-east-1"
    ECR_REPO = "920373001365.dkr.ecr.us-east-1.amazonaws.com/java-app-repo"
  }

  stages {
    stage('Build JAR') {
      steps {
        sh 'mvn clean package -DskipTests'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t $IMAGE_NAME:$TAG .'
      }
    }

    stage('Push to Amazon ECR') {
      steps {
        sh '''
          aws ecr get-login-password --region $AWS_REGION | docker login --username AWS --password-stdin $ECR_REPO
          docker tag $IMAGE_NAME:$TAG $ECR_REPO:$TAG
          docker push $ECR_REPO:$TAG
        '''
      }
    }
  }
}

