pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the project...'
                    sh 'g++ -o hello_exec hello_nonexistent.cpp' // Intentional error
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Testing the project...'
                    sh './hello_exec' 
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying the project...'
                }
            }
        }
    }

    post {
        failure {
            script {
                echo 'Pipeline failed. Please check errors.'
            }
        }
    }
}
