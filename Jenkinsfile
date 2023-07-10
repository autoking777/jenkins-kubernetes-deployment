pipeline {
  environment {
    dockerimagename = "autoking777/react-app"
    dockerImage = ""
    
agent any
  stages {
    stage('Cloning Git') {
      steps {
        git([url: 'git branch: 'main', credentialsId: 'github-credentials', url: 'https://github.com/autoking777/jenkins-kubernetes-deployment.git'])
  }
}
  }
}
    stage('Build image') {
      steps{
        script {
          dockerImage = docker.build dockerimagename
        }
      }
    }
