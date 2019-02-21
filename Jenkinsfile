pipeline {
  agent any
  options { 
    disableConcurrentBuilds()
  }
  triggers {
    pollSCM('H(0-4) H * * *')
  }
  stages {
    stage('Echo Branch') {
      agent any
      steps {
        sh 'echo "BUILDING BRANCH - ${GIT_BRANCH}"'
        sh 'sleep 15'
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
