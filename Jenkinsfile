pipeline {
    agent any

    environment {
        DOCKER_CREDENTIALS_ID = 'docker-hub-creds'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/ton-user/ton-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', DOCKER_CREDENTIALS_ID) {
                        def app = docker.build("ton-user/ton-image:latest")
                        app.push()
                    }
                }
            }
        }
    }
}
