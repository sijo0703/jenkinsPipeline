pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull the latest code from the Git repository
                git branch: 'master', url: 'https://github.com/sijo0703/jenkinsPipeline.git'
                println "Checkout completed"
            }
        }

        stage('Build') {
            steps {
                // Install dependencies (in this case, pytest for testing)
                sh 'pip install -r requirements.txt'
                println "Build completed"
            }
        }

        stage('Test') {
            steps {
                // Run the tests using pytest
                sh 'pytest tests/'
                println "Tests completed"
            }
        }

        stage('Package') {
            steps {
                // Package the application
                sh 'echo "Packaging the application..."'
                sh 'tar -czf myapp.tar.gz src/'
                println "Packaging completed"
            }
        }

        stage('Deploy') {
            steps {
                // Dummy deploy step
                sh 'echo "Deploying the application..."'
                println "Deploy completed"
            }
        }
    }

    post {
        always {
            // Cleanup the workspace
            cleanWs()
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
