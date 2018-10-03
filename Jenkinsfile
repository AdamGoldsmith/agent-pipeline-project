pipeline {

  // agent { label "master" }
  agent { label "DO-S1" }
/*    label {
      label "DO-S1"
    }
  }
*/
  environment {
    MESSAGE="Hello World"
    // you can set dynamic environment variables like this
    CM = """${sh(
        returnStdout: true,
        script: 'git log -1 --pretty=%B'
    )}"""
  }

  stages {

    // clean out the existing workspace
    stage ('clean workspace') {
      steps {
        step([$class: 'WsCleanup'])
      }
    }

    // perform a checkout of the repo specified in the Jenkins job
    stage('checkout') {
      steps {
         checkout scm
      }
    }

    // print message
    stage('print message') {
      steps {
        sh 'echo "${MESSAGE}\n${CM}"'
      }
    }
  }
}

