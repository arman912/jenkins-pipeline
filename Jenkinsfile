pipeline {
  agent any
  
  stage{
    stage('Checkout code') {
        steps {
            checkout scm
        }
    stage('Build'){
      steps {
        echo 'build'
      }
    stage('Test'){
      steps {
        echo 'test'
      }
    stage('Deploy'){
      steps {
        echo 'deploy'
      }
  }
}
