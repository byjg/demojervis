pipeline {
  agent any
  environment {
    IMAGE     = "aurea-demojervis:$BUILD_NUMBER"
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build . -t $IMAGE'
      }
    }
  }
}
