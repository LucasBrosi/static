pipeline {
  agent any
  stages {
    stage ('Lint HTML') {
      steps {
        sh 'echo "start to lint"'
        sh 'tidy -q -e *.html'
        sh 'echo "Linting complete"'
      }
    }    
    stage ('Upload to AWS') {
      steps {
        withAWSCli(credentials: 'AWS_Jenkins', region: 'us-east-2') {
          sh 'aws s3 ls'
          s3Upload(file:'index.html', bucket:'udacity-lucasb-jenkins01', path:'index.html')
        }
      }
    } 
  }
}

        
