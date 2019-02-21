pipeline {
  agent any
  options { 
    disableConcurrentBuilds()
    overrideIndexTriggers(false)
  }
  triggers {
    pollSCM('* H/10 * * *')
  }
  parameters {
    string(name: 'BD_PROJECT', defaultValue: 'myproject', description: 'Black Duck Project Name')
  }
  environment {
    BD_ARTIFACT_DIR = "\${WORKSPACE}/mydir"
  }
  stages {
    stage('Echo DIR') {
      agent any
      steps {
        sh "echo \"BD_ARTIFACT_DIR - ${BD_ARTIFACT_DIR}\""
        sh 'sleep 15'
      }
    }
    stage('Echo Branch') {
      agent any
      steps {
        sh 'echo "BUILDING BRANCH - ${GIT_BRANCH}"'
        sh 'sleep 15'
      }
    }
    stage('Echo Black Duck Project') {
      agent any
      steps {
        sh "echo 'PROJECT NAME - ${params.BD_PROJECT}'"
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
