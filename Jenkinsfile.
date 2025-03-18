pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'g++ working.cpp -o working_exec'
                echo 'Build stage completed successfully'
            }
        }
        stage('Test') {
            steps {
                bat 'working_exec'
                echo 'Test stage completed successfully'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                bat 'copy working_exec C:\\deploy\\working_exec'
                echo 'Deploy stage completed successfully'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed!'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
    }
}
