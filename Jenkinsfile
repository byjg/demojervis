pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build . -t $IMAGE'
      }
    }
  }
  environment {
    IMAGE = "aurea-demojervis:$BUILD_NUMBER"
    DOCKER_LOGIN = credentials("DOCKER_LOGIN")
  }
}
