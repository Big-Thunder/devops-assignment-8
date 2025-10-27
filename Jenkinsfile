pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "shubham0045/demo-app"
        DOCKER_TAG = "latest"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Big-Thunder/devops-assignment-8'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building the application...'
                // If it's a simple HTML site, skip build commands
                // For Node.js, Python, or Java, you’d run build commands here (e.g., npm install, mvn package, etc.)
            }
        }

        stage('Docker Build') {
            steps {
                script {
                    bat "docker build -t ${DOCKER_IMAGE}:${DOCKER_TAG} ."
                }
            }
        }

        stage('Docker Run') {
            steps {
                script {
                    bat "docker run -d -p 8090:80 ${DOCKER_IMAGE}:${DOCKER_TAG}"
                }
            }
        }

        stage('Post Cleanup') {
            steps {
                echo 'Build and container run completed successfully!'
            }
        }
    }
}
