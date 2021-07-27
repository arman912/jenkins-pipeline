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
     echo "${BUILD_URL} has result success"
      }
 failure {
     echo "${BUILD_URL} has result fail"
      }
     }
}
