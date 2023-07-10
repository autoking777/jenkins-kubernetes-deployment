pipeline {
  agent any
  
  stages {
    stage('Checkout Source') {
      steps {
        git 'https://github.com/autoking777/jenkins-kubernetes-deployment.git'
  }
    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build dockerimagename
        }
      }
    }
