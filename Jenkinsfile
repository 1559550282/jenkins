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
        sh '''aws s3 cp s3://$S3BUCKET/$S3PREFIX/packaged.yaml .
<<<<<<< HEAD
sam deploy --template-file packaged.yaml --stack-name $SAMSTACKNAME --capabilities CAPABILITY_IAM --region cn-northwest-1'''
=======
/usr/local/bin/sam deploy --template-file packaged.yaml --stack-name $SAMSTACKNAME --capabilities CAPABILITY_IAM --region cn-northwest-1'''
>>>>>>> b1fd7a38dc9b3a8b082d0dc012ea8acff7046160
      }
    }

  }
  environment {
    S3BUCKET = 'sharon199'
    S3PREFIX = 'build'
    SAMSTACKNAME = 'serverless-cicd-demo-stack'
  }
}