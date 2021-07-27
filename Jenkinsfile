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
            return env.BRANCH_NAME != 'main';
        }
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
