pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Prathmesh-502/node-docker-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("nodeapp:v1")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
               bat 'docker run -d -p 8082:8083 --name nodeapp nodeapp:v1'
            }
        }
    }
}
