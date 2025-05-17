pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = 'dockerhub'
        IMAGE_NAME = 'mohabouta/hello-jenkins'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/MOHAMEDBOUTALMAOUINE/Jenkins-Hello-World'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.withRegistry('', "${DOCKERHUB_CREDENTIALS}") {
                        def customImage = docker.build("${IMAGE_NAME}")
                        customImage.push()
                    }
                }
            }
        }
    }
}
