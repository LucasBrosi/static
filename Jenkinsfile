pipeline {
  agent any
  stages {
    stage ('Upload to AWS.') {
      steps {
        withAWS(credentials: 'aws-static', region: 'us-east-2') {
          s3Upload(file:'index.html', bucket:'udacity-lucasb-jenkins01', path:'index.html')
        }
      }
    }
  }
}

        
