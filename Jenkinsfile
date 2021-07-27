pipeline {
  agent any
  environment {
    APP_VERSION = '1.0.0'
    JENKINS_SERVERCREDS = credentials('jenkins')
  }
  
  stages{
    
    stage('Checkout code') {
        steps {
            checkout scm
        }
    }
    stage('Build'){
      steps {
        echo "building software app ${APP_VERSION}"
      }
    }
    stage('Test'){
      steps {
        echo 'test'
      }
    }
    stage('Deploy'){
      when {
          expression {
            BRANCH_NAME = 'dev' || BRANCH_NAME == 'test'
          }
        }
      steps {
        echo 'deploy'
        withCredentials([
          usernamePassword(credentails: 'jenkins',usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')] {
           sh 'echo deploy'
        }
      }
     }
  }
post {
  always {
    echo "${currentBuild.currentResult}"
  }
 success {
     echo "${env.BUILD_URL} has result success"
      }
 failure {
     echo "${env.BUILD_URL} has result fail"
      }
     }
}
