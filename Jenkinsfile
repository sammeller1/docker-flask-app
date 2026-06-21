pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/sammeller1/docker-flask-app.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t flask-hello-jenkins .'
            }
        }
        stage('Verify Image') {
            steps {
                sh 'docker images flask-hello-jenkins'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! Image built by Jenkins.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
