pipeline {
  agent any
  triggers {
      pollSCM('0 0 * * 0')
  }
  stages {
    stage('Echo Branch') {
      agent any
      steps {
        sh 'echo "BUILDING BRANCH - ${GIT_BRANCH}"'
      }
    }
    stage('Master') {
      when {
           branch 'master'
     }
      steps {
        sh 'echo "SHOULD ONLY RUN ON MASTER - ${GIT_BRANCH}"'
      }
    }
    stage('Develop') {
      when {
           branch 'develop'
     }
      steps {
        sh 'echo "SHOULD ONLY RUN ON DEVELOP - ${GIT_BRANCH}"'
      }
    }
  }
}
