pipeline {
    agent { docker { image 'python:3.7.2' } }
 
  environment {
    PATH = "${env.PATH};C:\\Windows\\System32"
  }

    stages {
        stage('Build') {
            steps {
                bat 'python hello.py'
            }
        }
        
        
    }
}
