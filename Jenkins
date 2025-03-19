pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'g++ working.cpp -o working_exec'
                echo 'Build stage completed successfully'
            }
        }
        stage('Test') {
            steps {
                sh './working_exec'
                echo 'Test stage completed successfully'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'cp working_exec /tmp/working_exec'
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
