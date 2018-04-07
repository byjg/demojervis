pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''export IMAGE="aurea-demojervis:$BUILD_NUMBER"
docker build . -t $IMAGE'''
      }
    }
    stage('Deploy') {
      steps {
        sh 'docker push $IMAGE'
      }
    }
  }
}