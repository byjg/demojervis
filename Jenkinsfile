pipeline {
  agent any
  stages {
    stage('CHECK') {
      steps {
        sh 'echo $DOCKER_LOGIN'
      }
    }
    // -----------------------------------------------------------------------
    // To use this Stage is necessary to install the Plugin "Copy Artifact"
    // -----------------------------------------------------------------------
    // stage('pull artifact') {
    //   steps {
    //     step([  $class: 'CopyArtifact',
    //             filter: 'hello-world-war-1.0.0.war',
    //             fingerprintArtifacts: true,
    //             projectName: '${JOB_NAME}',
    //             selector: [$class: 'SpecificBuildSelector', buildNumber: '${BUILD_NUMBER}']
    //     ])
    //     sh 'ls -la hello-world-war-1.0.0.war'
    //   }
    // }
    stage('Simulated deploy') {
      steps {
          sh 'find . -type f'
          unstash 'artifacts'
          sh 'find . -type f'
      }
    }
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
