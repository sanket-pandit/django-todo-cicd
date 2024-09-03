pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'develop',
                    url: 'https://github.com/sanket-pandit/django-todo-cicd.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t todo-app -f Dockerfile.app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8000:8000 todo-app'
            }
        }
    }
}
