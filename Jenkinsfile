pipeline {
  agent any
  
  stages{
    
    stage('Checkout code') {
        steps {
            checkout scm
        }
    }
    stage('Build'){
      steps {
        echo 'build'
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
