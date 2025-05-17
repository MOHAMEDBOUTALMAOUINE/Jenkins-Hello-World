pipeline {
    agent any

    environment {
        DOCKER_CREDENTIALS_ID = 'dockerhub' // Mets ici l'ID correct
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/MOHAMEDBOUTALMAOUINE/Jenkins-Hello-World'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', "${DOCKER_CREDENTIALS_ID}") {
                        def app = docker.build("ton-user/ton-image:latest")
                        app.push()
                    }
                }
            }
        }
    }
}
