pipeline {
  agent any
  stages {
    stage('Echo Branch') {
      agent any
      steps {
        sh 'echo "BUILDING BRANCH - ${GIT_BRANCH}"'
      }
    }
    stage('Master') {
      steps {
        sh 'echo "SHOULD ONLY RUN ON MASTER - ${GIT_BRANCH}"'
      }
    }
    stage('Develop') {
      steps {
        sh 'echo "SHOULD ONLY RUN ON DEVELOP - ${GIT_BRANCH}"'
      }
    }
  }
}