pipeline {
    agent any

    environment {
        IMAGE_NAME = "mohamedassal/myapp-dev"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'dev',
                    url: 'https://github.com/mohamed3ssal/Jenkins-With-Docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh """
                    docker build -t ${IMAGE_NAME}:${env.BUILD_NUMBER} .
                """
            }
        }

        stage('Run Container') {
            steps {
                sh """
                    docker run -d --name myapp_dev_${env.BUILD_NUMBER} -p 8080:80 ${IMAGE_NAME}:${env.BUILD_NUMBER}
                """
            }
        }
    }
}
