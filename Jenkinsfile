pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'feature/test',
                    url: 'https://github.com/mohamed3ssal/Jenkins-With-Docker.git'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh 'echo "Running tests on feature/test branch..."'
            }
        }
    }
}
