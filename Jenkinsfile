pipeline {
  agent any
  stages {
    stage ('Lint HTML.') {
      steps {
        tidy -q -e index.html
      }
    },    
    stage ('Upload to AWS.') {
      steps {
        withAWS(credentials: 'aws-static', region: 'us-east-2') {
          s3Upload(file:'index.html', bucket:'udacity-lucasb-jenkins01', path:'index.html')
        }
      }
    } 
  }
}

        
