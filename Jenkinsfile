pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone la branche main
                git branch: 'main', url: 'https://github.com/MOHAMEDBOUTALMAOUINE/Jenkins-Hello-World'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Construire une image Docker avec le tag "myapp:latest"
                    docker.build('myapp:latest')
                }
            }
        }
    }
}
