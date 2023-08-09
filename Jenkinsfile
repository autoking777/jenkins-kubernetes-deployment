pipeline {
    agent any

    environment {
        dockerimagename = "autoking777/react-app"
        dockerImage = ""
        registryCredential = 'dockerhub-credentials'
    }

    stages {
        stage('Checkout Source') {
            steps {
                git 'https://github.com/autoking777/jenkins-kubernetes-deployment.git'
            }
        }

        stage('Build Image') {
            steps {
                script {
                    dockerImage = docker.build dockerimagename
                }
            }
        }

        stage('Push Image to DockerHub') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', registryCredential) {
                        dockerImage.push("latest")
                    }
                }
            }
        }

        stage('Deploy React.js to Kubernetes') {
            steps {
                script {
                    kubernetesDeploy(configs: "deployment.yaml", "service.yaml")
                }
            }
        }
    }
}
