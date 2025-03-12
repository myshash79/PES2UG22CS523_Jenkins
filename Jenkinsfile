pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                    cd main  # Move to the correct directory
                    ls -l  # Verify hello.cpp exists
                    g++ hello.cpp -o hello_exec
                '''
            }
        }
        
        stage('Test') {
            steps {
                sh '''
                    cd main  # Move to the correct directory
                    ./hello_exec
                '''
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
