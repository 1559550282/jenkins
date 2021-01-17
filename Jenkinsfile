pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Pipeline for Test Env'
        build 'jenkins'
        echo 'Finished build'
      }
    }

    stage('Deploy') {
      steps {
        input 'Need Approval for Deployment'
        echo 'Now deploy application'
        sh 'aws s3 cp s3://sharon199/build/packaged.yaml .'
      }
    }

  }
  environment {
    S3BUCKET = 'sharon199'
    S3PREFIX = 'build'
    SAMSTACKNAME = 'serverless-cicd-demo-stack'
  }
}