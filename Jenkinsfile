pipeline {
    agent any  // Use any available agent, or specify a specific one if needed

    environment {
        GIT_REPO_URL = 'https://github.com/spoorti3/firstrepository.git'  // Replace with your repository URL
        BRANCH_NAME = 'main'  // Replace with your target branch
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone code from Git repository
                git url: "${GIT_REPO_URL}", branch: "${BRANCH_NAME}", credentialsId: 'GitHub-credentials'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add your build commands here. For example:
                // sh 'mvn clean package'  // For Maven projects
                // sh 'npm install'  // For Node.js projects
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test commands here. For example:
                // sh 'mvn test'  // For Maven projects
                // sh 'npm test'  // For Node.js projects
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deploy commands here. For example:
                // sh 'docker-compose up -d'  // For Docker deployments
                // sh 'kubectl apply -f deployment.yaml'  // For Kubernetes deployments
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
