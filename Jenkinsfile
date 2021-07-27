pipeline {
  agent any
  environment {
    APP_VERSION = '1.0.0'
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
            env.BRANCH_NAME == 'master' || env.BRANCH_NAME == 'main'
          }
        }
      steps {
        withCredentials([usernamePassword(credentialsId: 'jenkins', usernameVariable: USER, passwordVariable: PASSWORD)]){
          sh "echo ${USER} ${PASSWORD}"
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
